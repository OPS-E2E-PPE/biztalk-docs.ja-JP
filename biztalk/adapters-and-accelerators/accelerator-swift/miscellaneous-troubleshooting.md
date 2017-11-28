---
title: "その他のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: troubleshooting
ms.assetid: 6ebc1867-b5d3-46de-b3bd-69e570ed2b2c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765b32895fa76c0c77b740b76e2e6a03f0571351
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="miscellaneous-troubleshooting"></a><span data-ttu-id="d1710-102">その他のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d1710-102">Miscellaneous Troubleshooting</span></span>
## <a name="leading-zeroes-validation-is-not-performed-for-fields-that-use-the-checkleadingzeroesinelement-method-to-validate-a-field-in-the-message-validation-policy"></a><span data-ttu-id="d1710-103">先頭のゼロ CheckLeadingZeroesInElement メソッドを使用して、メッセージ検証ポリシー内のフィールドを検証するフィールドの検証が行われません。</span><span class="sxs-lookup"><span data-stu-id="d1710-103">Leading zeroes validation is not performed for fields that use the CheckLeadingZeroesInElement method to validate a field in the message Validation Policy.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="d1710-104">現象</span><span class="sxs-lookup"><span data-stu-id="d1710-104">Symptom</span></span>  
 <span data-ttu-id="d1710-105">フィールドには、先頭のゼロは許可されていないと、検証ポリシーには、この検証を実行するフィールドの規則が含まれています。 場合でも、フィールドに伴い、先行ゼロでメッセージが送信された場合、BRE の妥当性確認エラーは返されません。</span><span class="sxs-lookup"><span data-stu-id="d1710-105">No BRE validation error is returned if a message is submitted with leading zeroes in a field, even though leading zeroes are not permitted for the field and the validation policy includes a rule for the field that performs this validation.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="d1710-106">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="d1710-106">Possible Cause</span></span>  
 <span data-ttu-id="d1710-107">**CheckLeadingZeroInElement**メソッドは、メッセージの種類の検証ポリシーでビジネス ルールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1710-107">The **CheckLeadingZeroInElement** method is included in a business rule in the validation policy for the message type.</span></span> <span data-ttu-id="d1710-108">このメソッドは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="d1710-108">This method is deprecated.</span></span> <span data-ttu-id="d1710-109">関数呼び出しの目的は、検証、関数呼び出しで指定された要素が先頭にゼロがある場合のエラーを引き起こすを開始します。</span><span class="sxs-lookup"><span data-stu-id="d1710-109">The purpose of the function call is to cause validation to fail if there is a leading zero in the element provided in the function call.</span></span> <span data-ttu-id="d1710-110">ただし、フィールドに、先行ゼロがある場合でも、このメソッドは検証に失敗を発生しません。</span><span class="sxs-lookup"><span data-stu-id="d1710-110">However, this method does not cause validation to fail, even if there is a leading zero in the field.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="d1710-111">解決方法</span><span class="sxs-lookup"><span data-stu-id="d1710-111">Solution</span></span>  
 <span data-ttu-id="d1710-112">実装する必要がありますを伴い、先行ゼロをチェックする場合、 **CheckLeadingZero**メソッドの代わりに、 **CheckLeadingZeroInElement**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="d1710-112">If you want to check leading zeroes, you must implement the **CheckLeadingZero** method instead of the **CheckLeadingZeroInElement** method.</span></span> <span data-ttu-id="d1710-113">**CheckLeadingZero**関数への入力を文字列に先行ゼロがある場合、検証エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d1710-113">**CheckLeadingZero** causes a validation error if there is a leading zero in the string input to the function.</span></span>  
  
 <span data-ttu-id="d1710-114">実装する、 **CheckLeadingZero**メソッドを呼び出すカスタム メソッドを作成する必要があります、 **CheckLeadingZero**ユーザー定義関数内からメソッドを文字列としての値を提供して先頭のゼロを検証します。</span><span class="sxs-lookup"><span data-stu-id="d1710-114">To implement the **CheckLeadingZero** method, you must create a custom method that invokes the **CheckLeadingZero** method from within the custom function and provides to it as a string the value to be validated for leading zeroes.</span></span> <span data-ttu-id="d1710-115">これは、ため**CheckLeadingZero** 、エラー ログに記録しませんが、代わりに単に返すブール値 False、入力文字列が有効な SWIFT 数値フィールドではない場合、または入力文字列に先行ゼロがある場合。</span><span class="sxs-lookup"><span data-stu-id="d1710-115">This is because **CheckLeadingZero** does not log an error, but instead simply returns a Boolean False if the input string is not a valid SWIFT Number field or if the string input has a leading zero.</span></span> <span data-ttu-id="d1710-116">それ以外の場合、True を返します。</span><span class="sxs-lookup"><span data-stu-id="d1710-116">Otherwise, it returns True.</span></span> <span data-ttu-id="d1710-117">カスタム メソッドはそれに応じてエラーをログインし、実行できます。</span><span class="sxs-lookup"><span data-stu-id="d1710-117">Your custom method can then log errors accordingly.</span></span>  
  
## <a name="an-error-is-returned-by-the-message-validation-policy-if-the-swift-number-field-has-a-leading-zero"></a><span data-ttu-id="d1710-118">SWIFT 番号フィールドに、先行ゼロがある場合、メッセージ検証ポリシーによって、エラーが返されます</span><span class="sxs-lookup"><span data-stu-id="d1710-118">An error is returned by the message validation policy if the SWIFT Number field has a leading zero</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="d1710-119">現象</span><span class="sxs-lookup"><span data-stu-id="d1710-119">Symptom</span></span>  
 <span data-ttu-id="d1710-120">メッセージが送信されるフィールドに先行ゼロを場合でも、先頭のゼロがフィールドで許可されている場合は、BRE の検証エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="d1710-120">A BRE validation error is returned if a message is submitted with leading zeroes in a field even though leading zeroes are permitted for the field.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="d1710-121">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="d1710-121">Possible Cause</span></span>  
 <span data-ttu-id="d1710-122">これは、次のいずれかの使用に関する、通常、ルールのアクションの一部のルールに SWIFT 番号フィールドを検証する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="d1710-122">This can occur if one of the following methods is used to validate a SWIFT Number field in the rule concerned, usually in the Action part of the rule.</span></span> <span data-ttu-id="d1710-123">これは、量やレート、価格、数量フィールドで発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1710-123">This may occur in an Amount, Rate, Price, or Quantity field.</span></span>  
  
-   <span data-ttu-id="d1710-124">**CheckCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="d1710-124">**CheckCurrencyAmount**</span></span>  
  
-   <span data-ttu-id="d1710-125">**CheckValidAmount**</span><span class="sxs-lookup"><span data-stu-id="d1710-125">**CheckValidAmount**</span></span>  
  
-   <span data-ttu-id="d1710-126">**CheckValidCurrencyAndPriceCode**</span><span class="sxs-lookup"><span data-stu-id="d1710-126">**CheckValidCurrencyAndPriceCode**</span></span>  
  
-   <span data-ttu-id="d1710-127">**CheckValidSignCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="d1710-127">**CheckValidSignCurrencyAmount**</span></span>  
  
-   <span data-ttu-id="d1710-128">**CheckValidSignDateCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="d1710-128">**CheckValidSignDateCurrencyAmount**</span></span>  
  
-   <span data-ttu-id="d1710-129">**CheckValidSignRate**</span><span class="sxs-lookup"><span data-stu-id="d1710-129">**CheckValidSignRate**</span></span>  
  
-   <span data-ttu-id="d1710-130">**IsValidTransactionDetailsCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="d1710-130">**IsValidTransactionDetailsCurrencyAmount**</span></span>  
  
### <a name="solution"></a><span data-ttu-id="d1710-131">解決方法</span><span class="sxs-lookup"><span data-stu-id="d1710-131">Solution</span></span>  
 <span data-ttu-id="d1710-132">場合は、上記のリスト内のいずれかの除く**CheckValidSignRate**、ルールの検証ポリシーを有効にする」の説明に従って、先行ゼロで使用される[量フィールドの検証時に先行ゼロをサポートする](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md).</span><span class="sxs-lookup"><span data-stu-id="d1710-132">If any of the methods in the list above, except for **CheckValidSignRate**, is used in the rule in the Validation policy, enable leading zeros as described in [Supporting Leading Zeros in Amount Field Validations](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md).</span></span>  
  
 <span data-ttu-id="d1710-133">場合、 **CheckValidSignRate**メソッドがこのエラーを返したルールで使用される、伴い、先行ゼロをサポートする唯一の方法は、検証ポリシーからこのルールを削除します。</span><span class="sxs-lookup"><span data-stu-id="d1710-133">If the **CheckValidSignRate** method is used in the rule that returned this error, the only way to support leading zeroes is to remove this rule from the Validation policy.</span></span> <span data-ttu-id="d1710-134">これを実現するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d1710-134">Follow the steps below to accomplish this:</span></span>  
  
1.  <span data-ttu-id="d1710-135">ビジネス ルール作成ツールで右クリックし、**バージョン**ノードを展開したポリシーを使用してルールを含む、 **CheckValidSignRate**メソッドです。</span><span class="sxs-lookup"><span data-stu-id="d1710-135">In Business Rule Composer, right-click the **Version** node for the deployed policy that contains a rule using the **CheckValidSignRate** method.</span></span> <span data-ttu-id="d1710-136">をクリックして**展開解除**です。</span><span class="sxs-lookup"><span data-stu-id="d1710-136">Click **Undeploy**.</span></span>  
  
2.  <span data-ttu-id="d1710-137">右クリックし、**バージョン**ノードをクリックして同じポリシー、**コピー**です。</span><span class="sxs-lookup"><span data-stu-id="d1710-137">Right-click the **Version** node for the same policy, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="d1710-138">右クリックし、 **Validation_Policy**ノードをクリックして同じポリシー、**貼り付け**です。</span><span class="sxs-lookup"><span data-stu-id="d1710-138">Right-click the **Validation_Policy** node for the same policy, and then click **Paste**.</span></span>  
  
4.  <span data-ttu-id="d1710-139">新しい保存されていないバージョンのポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="d1710-139">Expand the new unsaved version of the policy.</span></span> <span data-ttu-id="d1710-140">持つルールを右クリックし、 **CheckValidSignRate**クリックしてメソッドを呼び出す**削除**です。</span><span class="sxs-lookup"><span data-stu-id="d1710-140">Right-click the rule that has the **CheckValidSignRate** method call, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="d1710-141">ポリシー未保存の新しい右クリックして**バージョン**ノードをクリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="d1710-141">Right-click the policy's new unsaved **Version** node, and then click **Save**.</span></span> <span data-ttu-id="d1710-142">同じノードを右クリックし、をクリックして**発行**です。</span><span class="sxs-lookup"><span data-stu-id="d1710-142">Right-click the same node, and then click **Publish**.</span></span> <span data-ttu-id="d1710-143">同じノードを右クリックし、をクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="d1710-143">Right-click the same node, and then click **Deploy**.</span></span>  
  
## <a name="a4swift-database-requires-archiving"></a><span data-ttu-id="d1710-144">A4SWIFT データベースでは、アーカイブが必要です。</span><span class="sxs-lookup"><span data-stu-id="d1710-144">A4SWIFT database requires archiving</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="d1710-145">現象</span><span class="sxs-lookup"><span data-stu-id="d1710-145">Symptom</span></span>  
 <span data-ttu-id="d1710-146">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースが大きくなりすぎます。</span><span class="sxs-lookup"><span data-stu-id="d1710-146">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database is growing too large.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="d1710-147">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="d1710-147">Possible Cause</span></span>  
 <span data-ttu-id="d1710-148">履歴テーブルで、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースが自動的にアーカイブされていません。</span><span class="sxs-lookup"><span data-stu-id="d1710-148">The History table in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database is not automatically archived.</span></span> <span data-ttu-id="d1710-149">次の表は、メッセージの修復と新しい送信、タスクと、オーケストレーション プロセスに関するデータを実行したユーザーなどに関するデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="d1710-149">This table stores data about message repair and new submission, including who performed which tasks and data about orchestration processes.</span></span> <span data-ttu-id="d1710-150">次の表は、メッセージの修復や新しい送信操作を行うにつれて続行されます。</span><span class="sxs-lookup"><span data-stu-id="d1710-150">This table will continue to grow as you perform message repair and new submission operations.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="d1710-151">解決方法</span><span class="sxs-lookup"><span data-stu-id="d1710-151">Solution</span></span>  
 <span data-ttu-id="d1710-152">増大を制限、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースを定期的にアーカイブのプロシージャの標準を使用して、履歴テーブルからデータをアーカイブします。</span><span class="sxs-lookup"><span data-stu-id="d1710-152">To limit growth of the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, routinely archive data out of the History table, using your standard archiving procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1710-153">参照</span><span class="sxs-lookup"><span data-stu-id="d1710-153">See Also</span></span>  
 [<span data-ttu-id="d1710-154">トラブルシューティング: 問題と解決策</span><span class="sxs-lookup"><span data-stu-id="d1710-154">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)