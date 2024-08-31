---
title : "Add Function Layer"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 4.3. </b> "
---

**Add Function Layer**


1. Inside the function page, move to the bottom of the page, you will see the **Layers** section. Click **Add a layer**.
    ![Lambda](/images/3.lambda/endpoint.png)
2. At the **Create bucket** page:
   - In the **Add Layer** page, choose **Custom layers** from **Layer Source** field. 
   - Then, after **Custom layers** field show up, choose the layer your have create in **4.2** and their version(for a newly created layer, it should be version 1).
   - Review the information and then Click **Add**.
    ![Lambda](/images/3.lambda/layera.png)
3. Verify the Layer Addition: You will be redirected back to the function page. Check if the layer has been imported by looking at the function diagram, where the number of layers in your function should now be visible.
    ![Lambda](/images/3.lambda/functiond.png)
4. (Optional) Verify the Library:

You can check if your library is working by testing the Requests library with this code snippet:
   
   ```python
import requests

response = requests.get("https://api.github.com")
print(response.status_code)

```
The setup is complete; let's move on to the content of the function.