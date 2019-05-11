---
title: その他のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 6ebc1867-b5d3-46de-b3bd-69e570ed2b2c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb284d6d869834e3e6d148e2582043e3789f43ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377188"
---
# <a name="miscellaneous-troubleshooting"></a><span data-ttu-id="ac158-102">その他のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ac158-102">Miscellaneous Troubleshooting</span></span>
## <a name="leading-zeroes-validation-is-not-performed-for-fields-that-use-the-checkleadingzeroesinelement-method-to-validate-a-field-in-the-message-validation-policy"></a><span data-ttu-id="ac158-103">先頭のゼロ CheckLeadingZeroesInElement メソッドを使用して、メッセージ検証ポリシー内のフィールドを検証するフィールドの検証が実行されません。</span><span class="sxs-lookup"><span data-stu-id="ac158-103">Leading zeroes validation is not performed for fields that use the CheckLeadingZeroesInElement method to validate a field in the message Validation Policy.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="ac158-104">現象</span><span class="sxs-lookup"><span data-stu-id="ac158-104">Symptom</span></span>  
 <span data-ttu-id="ac158-105">フィールドには、先頭のゼロは許可されていないと、検証ポリシーには、この検証を実行するフィールドのルールが含まれていますが、フィールドに先行ゼロをメッセージが送信される場合は、BRE の検証のエラーは返されません。</span><span class="sxs-lookup"><span data-stu-id="ac158-105">No BRE validation error is returned if a message is submitted with leading zeroes in a field, even though leading zeroes are not permitted for the field and the validation policy includes a rule for the field that performs this validation.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="ac158-106">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="ac158-106">Possible Cause</span></span>  
 <span data-ttu-id="ac158-107">**CheckLeadingZeroInElement**メソッドが、メッセージの種類の検証ポリシーでビジネス ルールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="ac158-107">The **CheckLeadingZeroInElement** method is included in a business rule in the validation policy for the message type.</span></span> <span data-ttu-id="ac158-108">このメソッドが非推奨とされます。</span><span class="sxs-lookup"><span data-stu-id="ac158-108">This method is deprecated.</span></span> <span data-ttu-id="ac158-109">関数呼び出しでは、検証、関数呼び出しで指定された要素が先頭にゼロがある場合のエラーを引き起こします。</span><span class="sxs-lookup"><span data-stu-id="ac158-109">The purpose of the function call is to cause validation to fail if there is a leading zero in the element provided in the function call.</span></span> <span data-ttu-id="ac158-110">ただし、フィールドに先行ゼロがある場合でも、このメソッドは検証に失敗を発生できません。</span><span class="sxs-lookup"><span data-stu-id="ac158-110">However, this method does not cause validation to fail, even if there is a leading zero in the field.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="ac158-111">ソリューション</span><span class="sxs-lookup"><span data-stu-id="ac158-111">Solution</span></span>  
 <span data-ttu-id="ac158-112">実装する必要がある先頭のゼロを確認する場合、 **CheckLeadingZero**メソッドの代わりに、 **CheckLeadingZeroInElement**メソッド。</span><span class="sxs-lookup"><span data-stu-id="ac158-112">If you want to check leading zeroes, you must implement the **CheckLeadingZero** method instead of the **CheckLeadingZeroInElement** method.</span></span> <span data-ttu-id="ac158-113">**CheckLeadingZero**関数への文字列入力に先行ゼロがある場合、検証エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="ac158-113">**CheckLeadingZero** causes a validation error if there is a leading zero in the string input to the function.</span></span>  
  
 <span data-ttu-id="ac158-114">実装する、 **CheckLeadingZero**メソッドを呼び出すカスタム メソッドを作成する必要があります、 **CheckLeadingZero**ユーザー定義関数内からメソッドを文字列として値を提供し、先頭のゼロを検証します。</span><span class="sxs-lookup"><span data-stu-id="ac158-114">To implement the **CheckLeadingZero** method, you must create a custom method that invokes the **CheckLeadingZero** method from within the custom function and provides to it as a string the value to be validated for leading zeroes.</span></span> <span data-ttu-id="ac158-115">これは、ため**CheckLeadingZero**エラーを記録しませんが、代わりに単に False を返します、ブール値、入力文字列が有効な SWIFT 数値フィールドではない場合、または文字列入力に先行ゼロがある場合。</span><span class="sxs-lookup"><span data-stu-id="ac158-115">This is because **CheckLeadingZero** does not log an error, but instead simply returns a Boolean False if the input string is not a valid SWIFT Number field or if the string input has a leading zero.</span></span> <span data-ttu-id="ac158-116">それ以外の場合、True を返します。</span><span class="sxs-lookup"><span data-stu-id="ac158-116">Otherwise, it returns True.</span></span> <span data-ttu-id="ac158-117">カスタム メソッドはエラーを適宜記録し、できます。</span><span class="sxs-lookup"><span data-stu-id="ac158-117">Your custom method can then log errors accordingly.</span></span>  
  
## <a name="an-error-is-returned-by-the-message-validation-policy-if-the-swift-number-field-has-a-leading-zero"></a><span data-ttu-id="ac158-118">SWIFT 番号フィールドに、先行ゼロがある場合、メッセージの検証ポリシーによってエラーが返されます</span><span class="sxs-lookup"><span data-stu-id="ac158-118">An error is returned by the message validation policy if the SWIFT Number field has a leading zero</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="ac158-119">現象</span><span class="sxs-lookup"><span data-stu-id="ac158-119">Symptom</span></span>  
 <span data-ttu-id="ac158-120">メッセージが送信される場合に、フィールドに先行ゼロ場合でも、先行するフィールドのゼロが許可されている、BRE の検証エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="ac158-120">A BRE validation error is returned if a message is submitted with leading zeroes in a field even though leading zeroes are permitted for the field.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="ac158-121">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="ac158-121">Possible Cause</span></span>  
 <span data-ttu-id="ac158-122">これは、次のメソッドのいずれかがにとっては、ルールのアクションの一部では、通常のルールで SWIFT 番号フィールドの検証に使用される場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="ac158-122">This can occur if one of the following methods is used to validate a SWIFT Number field in the rule concerned, usually in the Action part of the rule.</span></span> <span data-ttu-id="ac158-123">これは、量、速度、価格、または数量フィールドで発生します。</span><span class="sxs-lookup"><span data-stu-id="ac158-123">This may occur in an Amount, Rate, Price, or Quantity field.</span></span>  
  
-   <span data-ttu-id="ac158-124">**CheckCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="ac158-124">**CheckCurrencyAmount**</span></span>  
  
-   <span data-ttu-id="ac158-125">**CheckValidAmount**</span><span class="sxs-lookup"><span data-stu-id="ac158-125">**CheckValidAmount**</span></span>  
  
-   <span data-ttu-id="ac158-126">**CheckValidCurrencyAndPriceCode**</span><span class="sxs-lookup"><span data-stu-id="ac158-126">**CheckValidCurrencyAndPriceCode**</span></span>  
  
-   <span data-ttu-id="ac158-127">**CheckValidSignCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="ac158-127">**CheckValidSignCurrencyAmount**</span></span>  
  
-   <span data-ttu-id="ac158-128">**CheckValidSignDateCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="ac158-128">**CheckValidSignDateCurrencyAmount**</span></span>  
  
-   <span data-ttu-id="ac158-129">**CheckValidSignRate**</span><span class="sxs-lookup"><span data-stu-id="ac158-129">**CheckValidSignRate**</span></span>  
  
-   <span data-ttu-id="ac158-130">**IsValidTransactionDetailsCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="ac158-130">**IsValidTransactionDetailsCurrencyAmount**</span></span>  
  
### <a name="solution"></a><span data-ttu-id="ac158-131">ソリューション</span><span class="sxs-lookup"><span data-stu-id="ac158-131">Solution</span></span>  
 <span data-ttu-id="ac158-132">場合、上記のリスト内のメソッドのいずれか以外の**CheckValidSignRate**、検証ポリシーでは、先行するゼロ」の説明に従って有効にするルールで使用される、[量フィールド検証で先行ゼロをサポートしている](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md).</span><span class="sxs-lookup"><span data-stu-id="ac158-132">If any of the methods in the list above, except for **CheckValidSignRate**, is used in the rule in the Validation policy, enable leading zeros as described in [Supporting Leading Zeros in Amount Field Validations](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md).</span></span>  
  
 <span data-ttu-id="ac158-133">場合、 **CheckValidSignRate**メソッドがこのエラーを返したルールで使用される、先頭のゼロをサポートする唯一の方法は検証ポリシーからこのルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="ac158-133">If the **CheckValidSignRate** method is used in the rule that returned this error, the only way to support leading zeroes is to remove this rule from the Validation policy.</span></span> <span data-ttu-id="ac158-134">これを実現する次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ac158-134">Follow the steps below to accomplish this:</span></span>  
  
1.  <span data-ttu-id="ac158-135">ビジネス ルール作成ツールを右クリックし、**バージョン**ノードを展開したポリシーを使用して規則を含む、 **CheckValidSignRate**メソッド。</span><span class="sxs-lookup"><span data-stu-id="ac158-135">In Business Rule Composer, right-click the **Version** node for the deployed policy that contains a rule using the **CheckValidSignRate** method.</span></span> <span data-ttu-id="ac158-136">クリックして**展開解除**します。</span><span class="sxs-lookup"><span data-stu-id="ac158-136">Click **Undeploy**.</span></span>  
  
2.  <span data-ttu-id="ac158-137">右クリックし、**バージョン**同じポリシー、およびクリック ノード**コピー**します。</span><span class="sxs-lookup"><span data-stu-id="ac158-137">Right-click the **Version** node for the same policy, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="ac158-138">右クリックし、 **Validation_Policy**同じポリシー、およびクリック ノード**貼り付け**します。</span><span class="sxs-lookup"><span data-stu-id="ac158-138">Right-click the **Validation_Policy** node for the same policy, and then click **Paste**.</span></span>  
  
4.  <span data-ttu-id="ac158-139">新しい保存されていないバージョンのポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="ac158-139">Expand the new unsaved version of the policy.</span></span> <span data-ttu-id="ac158-140">持つルールを右クリックし、 **CheckValidSignRate**メソッドの呼び出しをクリック**削除**します。</span><span class="sxs-lookup"><span data-stu-id="ac158-140">Right-click the rule that has the **CheckValidSignRate** method call, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="ac158-141">ポリシーが保存されていない新しい右クリック**バージョン**ノード、およびクリック**保存**。</span><span class="sxs-lookup"><span data-stu-id="ac158-141">Right-click the policy's new unsaved **Version** node, and then click **Save**.</span></span> <span data-ttu-id="ac158-142">同じノードを右クリックし、をクリックし、**発行**します。</span><span class="sxs-lookup"><span data-stu-id="ac158-142">Right-click the same node, and then click **Publish**.</span></span> <span data-ttu-id="ac158-143">同じノードを右クリックし、をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="ac158-143">Right-click the same node, and then click **Deploy**.</span></span>  
  
## <a name="a4swift-database-requires-archiving"></a><span data-ttu-id="ac158-144">A4SWIFT データベースのアーカイブが必要です。</span><span class="sxs-lookup"><span data-stu-id="ac158-144">A4SWIFT database requires archiving</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="ac158-145">現象</span><span class="sxs-lookup"><span data-stu-id="ac158-145">Symptom</span></span>  
 <span data-ttu-id="ac158-146">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースが大きく増加しています。</span><span class="sxs-lookup"><span data-stu-id="ac158-146">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database is growing too large.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="ac158-147">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="ac158-147">Possible Cause</span></span>  
 <span data-ttu-id="ac158-148">履歴テーブルで、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースが自動的にアーカイブしていません。</span><span class="sxs-lookup"><span data-stu-id="ac158-148">The History table in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database is not automatically archived.</span></span> <span data-ttu-id="ac158-149">このテーブルには、メッセージの修復と新しい送信、タスクと、オーケストレーション プロセスに関するデータを実行したユーザーなどに関するデータが格納されます。</span><span class="sxs-lookup"><span data-stu-id="ac158-149">This table stores data about message repair and new submission, including who performed which tasks and data about orchestration processes.</span></span> <span data-ttu-id="ac158-150">このテーブルは、メッセージの修復と新しい送信の操作を実行するようを拡張し続けます。</span><span class="sxs-lookup"><span data-stu-id="ac158-150">This table will continue to grow as you perform message repair and new submission operations.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="ac158-151">ソリューション</span><span class="sxs-lookup"><span data-stu-id="ac158-151">Solution</span></span>  
 <span data-ttu-id="ac158-152">増加を制限する、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースで、標準のアーカイブのプロシージャを使用して、履歴テーブルからデータを定期的にアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="ac158-152">To limit growth of the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, routinely archive data out of the History table, using your standard archiving procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac158-153">参照</span><span class="sxs-lookup"><span data-stu-id="ac158-153">See Also</span></span>  
 [<span data-ttu-id="ac158-154">トラブルシューティング: 問題と解決方法</span><span class="sxs-lookup"><span data-stu-id="ac158-154">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)