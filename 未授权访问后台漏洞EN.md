For the HY511 PoE camera device from Hanyuan Technology, if the core panel is earlier than version 2.1, please visit the corresponding backend login page as shown in the image.

![image-20251025145415230](./未授权访问后台漏洞.assert/image-20251025145415230.png)

We access the following URL address through the direct page: 192.168.1.91/LAPI/V1.0/System/Configuration

Or send the following data packet by capturing the packet in burpSuite

![image-20251025145520365](./未授权访问后台漏洞.assert/image-20251025145520365.png)

We can directly download the corresponding core configuration file without logging into the backend, mainly because there is no verification of cookie identity information, etc.

![image-20251025145622990](./未授权访问后台漏洞.assert/image-20251025145622990.png)

![image-20251025145650214](./未授权访问后台漏洞.assert/image-20251025145650214.png)

Then we read the XML data in the configuration file and search for the admin-related information field to find the corresponding backend login password.

![image-20251025145743778](./未授权访问后台漏洞.assert/image-20251025145743778.png)

By decrypting with md5, we can directly obtain the corresponding password of the background, which is hy123456

![image-20251025145822200](./未授权访问后台漏洞.assert/image-20251025145822200.png)

Next we can log in directly to the corresponding background

![image-20251025145855302](./未授权访问后台漏洞.assert/image-20251025145855302.png)

![image-20251025145916490](./未授权访问后台漏洞.assert/image-20251025145916490.png)

At this point, we have bypassed the front-end backend login page and directly come to the backend management system, so that we can directly steal information and manage the entire camera.



