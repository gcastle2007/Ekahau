# Добавление регуляторного домена RU в FPMS (меню) на WLANPI

Идём в:
```
/opt/wlanpi-fpms/lib/python3.9/site-packages/fpms $ ls -la
```
Редактируем файл fpms.py:
```
sudo nano fpms.py
```
Ищем такой кусок кода:
```
    def show_reg_domain():
        system_obj = RegDomain(g_vars)
        system_obj.show_reg_domain(g_vars)

    def set_reg_domain_us():
        system_obj = RegDomain(g_vars)
        system_obj.set_reg_domain_us(g_vars)
```
Добавляем после него с соблюдением всей структуры и синтаксиса:
```
    def set_reg_domain_ru():
        system_obj = RegDomain(g_vars)
        system_obj.set_reg_domain_ru(g_vars)
```
Ищем дальше раздел:
```
    #######################
    # menu structure here
    #######################
```
Находите:
```
                {"name": "RF Domain", "action": [
                    {"name": "Show Domain", "action": show_reg_domain},
                    {"name": "Set Domain US", "action": [
                        {"name": "Confirm & Reboot", "action": set_reg_domain_us},]},
```
Добавляете в соответствие со структурой:
```
                    {"name": "Set Domain RU", "action": [
                        {"name": "Confirm & Reboot", "action": set_reg_domain_ru},]},
```
Чтобы получилось вот так:
```
                {"name": "RF Domain", "action": [
                    {"name": "Show Domain", "action": show_reg_domain},
                    {"name": "Set Domain RU", "action": [
                        {"name": "Confirm & Reboot", "action": set_reg_domain_ru},]},
                    {"name": "Set Domain US", "action": [
                        {"name": "Confirm & Reboot", "action": set_reg_domain_us},]},
```
Выходите с сохранением.

Дальше:
```
 cd modules/
 sudo nano reg_domain.py
 ```

Здесь ищем:
```
    def set_reg_domain_us(self, g_vars):
```
После этого блока вставляем:
```
    def set_reg_domain_ru(self, g_vars):
        self.alert_obj.display_popup_alert(g_vars, 'Setting domain', delay=2)

        try:
            alert_msg = subprocess.check_output(f"{REG_DOMAIN_FILE} set RU --no-prompt", shell=True).decode()
            time.sleep(1)
        except subprocess.CalledProcessError as exc:
            print(exc)
            self.alert_obj.display_alert_error(g_vars, 'Failed to set domain')
            g_vars['display_state'] = 'menu'
            return

        self.alert_obj.display_popup_alert(g_vars, 'Successfully set', delay=1)
        g_vars['display_state'] = 'menu'
        g_vars['shutdown_in_progress'] = True
        oled.drawImage(g_vars['reboot_image'])
        time.sleep(1)
        os.system('reboot')
        return
```
Перезапускаем WlanPi и радуемся жизни:

![](./images/ru_domain.PNG)
