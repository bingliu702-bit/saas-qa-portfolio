# Day 01 — Test Scenario Drafts

## SC-001: Verify Product List Display

### Test Objective

Verify that the product list is displayed correctly.

### Preconditions

The AcademyBugs website is accessible.

### Steps to Reproduce

1. Open the AcademyBugs website.
2. Navigate to the product list page.
3. Check the product images, names, prices, and action buttons.
4. Scroll down the page.

### Expected Result

- The product list page opens successfully.
- The main product information is clearly visible.
- There are no obvious overlapping, obstructed, or unusable elements.

### Actual Result

The product list page opens successfully.

In the same row, the product name, price, and **"Add to Cart"** button of the middle product, **"Dark Gray Jeans,"** are noticeably higher than those of the products on the left and right, **"DNK Yellow Shoes"** and **"Flamingo T-shirt."**

The three product cards are not vertically aligned.

### Execution

- **Attempts:** 2
- **Reproduction:** Reproduced in 2 out of 2 attempts (100%)
- **Test Result:** Fail

### Evidence

A screenshot of the product list page was saved as evidence.
<img width="744" height="341" alt="image" src="https://github.com/user-attachments/assets/63ef3262-9cda-47f4-b65c-c459c8f03a1e" />


## SC-002: Modify Product Quantity and Check Price

- **Test Objective:** Verify that the quantity can be modified and that the related price information is updated correctly.
- **Preconditions:** A product details page with an editable quantity field is open.
- **Test Data:** Increase the quantity from 1 to 3.

### Steps to Reproduce

1. Record the initial product price and quantity.
2. Click the **"+"** button to increase the quantity to 3.
3. Check the displayed quantity and price.

### Expected Result

- The quantity should be updated to 3.
- If the page displays a total price, the total should equal the unit price multiplied by 3.

### Actual Result

The initial quantity on the product details page is 1.

After clicking the **"+"** button, the quantity remains 1 and does not increase. Repeated clicks produce the same result.

After refreshing the page and repeating the test, the same result occurs.

When 3 is entered manually in the quantity field, the quantity is displayed as 3, but the page still shows a price of USD 45.00.

This price may represent the unit price. Whether the displayed price should be updated based on the quantity requires confirmation of the product requirements.

### Execution

- **Attempts:** 2
- **Reproduction:** The unresponsive **"+"** button was reproduced in 2 out of 2 attempts (100%).
- **Test Result:** Fail

### Evidence

A screenshot of the product details page was saved as evidence.

However, a static screenshot cannot fully demonstrate that the **"+"** button is unresponsive. A screen recording should be added to provide stronger evidence.
<img width="668" height="429" alt="image" src="https://github.com/user-attachments/assets/68d1c20b-ed1f-46cf-927a-a42af88e961a" />


## SC-003：将指定数量的商品加入购物车

- 测试目的：确认用户选择的商品和数量能够正确加入购物车。
- 前置条件：商品详情页已经打开，购物车功能可用。
- 测试数据：任意商品，数量为2。
- 操作步骤：
  1. 将商品数量设置为2。
  2. 点击“Add to cart”。
  3. 打开购物车。
  4. 核对商品名称、单价和数量。
- 预期结果：购物车中显示正确商品；商品数量为2；价格信息与商品页及计算规则一致。
- 实际观察：•	
•	手动将“DNK Yellow Shoes”的数量设置为2后，点击“Add to cart”，购物车成功显示了正确的商品名称、单价和数量。
•	
•	购物车显示：
•	- 商品单价：45.00美元
•	- 商品数量：2
•	- 商品小计：90.00美元
•	- 运费：7.99美元
•	- 页面实际显示的Grand Total：197.99美元
•	按照页面数据计算，正确总价应为：
•	90.00 + 7.99 = 97.99美元
•	但页面显示为197.99美元，比正确结果多出100.00美元。刷新页面并重新执行测试后，仍然出现相同结果。
•	执行次数：2次
•	复现结果：2/2次均出现错误总价
•	测试结果：Fail
•	证据：已保存购物车页面截图，截图中可以看到商品小计、运费和错误的Grand Total。
<img width="688" height="457" alt="image" src="https://github.com/user-attachments/assets/41ecef33-d2d4-4bcb-ab04-5660bd59b3bb" />


## SC-004：在购物车中查看和修改商品数量

- 测试目的：确认购物车能够显示并修改当前商品数量。
- 前置条件：购物车中已经存在至少一件商品。
- 操作步骤：
  1. 打开购物车。
  2. 查看当前商品数量。
  3. 点击“+”增加数量。
  4. 点击“-”减少数量。
  5. 查看商品小计和购物车总价。
- 预期结果：当前数量清晰可见；加减按钮有效；数量改变后，小计和总价按照规则更新。
- 实际观察：

1. 增加数量
购物车中“DNK Yellow Shoes”的初始数量为2，单价为45.00美元。点击“+”按钮后，数量成功增加为3。
但是商品Total和Cart Subtotal仍然显示90.00美元，没有按照数量3更新为135.00美元。
页面显示：
- 数量：3
- 单价：45.00美元
- 实际商品Total：90.00美元
- 预期商品Total：135.00美元
- 运费：7.99美元
- 实际Grand Total：197.99美元
- 预期Grand Total：142.99美元

2. 减少数量
将数量从2减少为1后，商品Total和Cart Subtotal正确更新为45.00美元，但Grand Total显示为152.99美元。
页面显示：
- 数量：1
- 单价：45.00美元
- 商品Total：45.00美元
- 运费：7.99美元
- 实际Grand Total：152.99美元
- 预期Grand Total：52.99美元
测试结果：Fail
失败原因：
- 数量增加到3后，商品Total和Cart Subtotal没有随数量更新。
- Grand Total在数量为3和数量为1时均计算错误。
证据：
- 截图1显示数量3、Cart Subtotal 90.00美元、Grand Total 197.99美元。
- 截图2显示数量1、Cart Subtotal 45.00美元、Grand Total 152.99美元。
<img width="992" height="494" alt="image" src="https://github.com/user-attachments/assets/44c05dcd-43da-448f-8c35-7e9e5121fbee" />
<img width="932" height="571" alt="image" src="https://github.com/user-attachments/assets/2391b47c-4329-4b62-8594-d70403c8daf5" />


## SC-005：切换商品显示货币

- 测试目的：确认切换货币后，货币符号和价格能够保持一致。
- 前置条件：页面提供货币切换功能。
- 操作步骤：
  1. 记录当前货币和一个商品的价格。
  2. 选择另一种货币。
  3. 查看商品列表或商品详情页中的货币符号和价格。
  4. 刷新页面后再次查看。
- 预期结果：页面使用所选择的目标货币；货币符号和商品价格按照产品规则更新。
- 实际观察：•	购物车页面初始货币为USD。分别选择EUR、GBP和[填写第三种实际测试的货币]后，页面均被黑色遮罩覆盖，并显示“You found a crash bug, examine the page for 5 seconds.”提示。
•	
•	出现该提示后，购物车页面无法继续正常操作，商品价格和货币符号也没有完成更新。刷新页面后，货币恢复为USD，页面可以再次操作。
•	
•	测试数据：
•	- EUR
•	- GBP
•	- [第三种货币]
•	
•	测试组数：3组不同货币
•	测试结果：3/3组均出现相同异常
•	最终结果：Fail
•	
•	证据：
•	已保存选择EUR后的页面截图。该截图显示EUR已被选中，页面出现黑色遮罩和Crash Bug提示。
<img width="1122" height="601" alt="image" src="https://github.com/user-attachments/assets/daec3ef7-f7c6-449b-840e-ff4b57a0660d" />

## Notes

## Execution Notes

以上5个测试场景已经执行，并已根据实际测试结果填写“实际观察”和“测试结果”。

测试结果中的Fail表示实际结果与预期结果不一致，但不一定自动等于已经确认的Bug。发现的异常仍需结合产品规则、重复测试和证据进行确认；确认的问题将另外整理为正式Bug报告。

- 测试环境：Windows 11，Google Chrome
- 浏览器版本：Google Chrome 版本 153.0.8010.50
- 测试日期：2026年9月21日
- 测试网站：AcademyBugs
