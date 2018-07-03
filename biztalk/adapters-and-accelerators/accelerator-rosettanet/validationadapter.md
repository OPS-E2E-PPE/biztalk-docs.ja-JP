---
title: ValidationAdapter |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5fe99350-14c0-4ddb-b257-af9a0c4258f6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbcf26ee8a3a97d2df34bb29dad5d0cf31d4db1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987907"
---
# <a name="validationadapter"></a><span data-ttu-id="7cd91-102">ValidationAdapter</span><span class="sxs-lookup"><span data-stu-id="7cd91-102">ValidationAdapter</span></span>
<span data-ttu-id="7cd91-103">ValidationAdapter のサンプルは、応答側パブリック プロセスでメッセージに対して特殊な検証ルールを実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7cd91-103">The ValidationAdapter sample demonstrates how to run special validation rules on a message in a responder public process.</span></span> <span data-ttu-id="7cd91-104">Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]ネイティブ送信で検証を実行します。 または、受信パイプライン、オーケストレーション内に存在します。</span><span class="sxs-lookup"><span data-stu-id="7cd91-104">Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] natively performs validation in the send or receive pipeline, and in orchestrations.</span></span> <span data-ttu-id="7cd91-105">追加の検証を実行する場合は、検証アダプターを作成します。</span><span class="sxs-lookup"><span data-stu-id="7cd91-105">If you want to perform additional validation, you can create a validation adapter.</span></span> <span data-ttu-id="7cd91-106">追加の検証には、クロスフィールド検証ルールや、XSD を使用して実装できないビジネス固有の検証ルールを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="7cd91-106">The additional validation could include cross-field validation or business-specific validation rules that you cannot implement using an XSD.</span></span>  
  
 <span data-ttu-id="7cd91-107">検証アダプターを作成するには追加することで[!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)]ValidationAdapter サンプルで、インターフェイスを公開して、アダプターをアグリーメントのプロパティに入力するコードです。</span><span class="sxs-lookup"><span data-stu-id="7cd91-107">You can create a validation adapter by adding [!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)] code to the ValidationAdapter sample, publishing the interfaces, and entering the adapter into the agreement properties.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="7cd91-108"> メッセージの処理中に、検証アダプターはし呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7cd91-108"> will then call the validation adapter during message processing.</span></span>  
  
 <span data-ttu-id="7cd91-109">ValidationAdapter はパブリック プロセス オーケストレーションで使用されるため、そのオーケストレーションをホストしている BizTalk ホスト サービスと同じ資格情報の下に実行されます。</span><span class="sxs-lookup"><span data-stu-id="7cd91-109">Since the ValidationAdapter is used by the public process orchestration , it runs under the same credentials as the BizTalk host service hosting that orchestration.</span></span>  
  
 <span data-ttu-id="7cd91-110">ValidationAdapter サンプルはあります\<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\ValidationAdapter します。</span><span class="sxs-lookup"><span data-stu-id="7cd91-110">The ValidationAdapter sample is located in \<*drive*\>:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\ValidationAdapter.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="7cd91-111">使用例</span><span class="sxs-lookup"><span data-stu-id="7cd91-111">Demonstrates</span></span>  
 <span data-ttu-id="7cd91-112">ValidationAdapter サンプルは、サービス コンテンツでの電子メール アドレスの検証を示します。</span><span class="sxs-lookup"><span data-stu-id="7cd91-112">The ValidationAdapter sample demonstrates validation of the e-mail address in the service content.</span></span> <span data-ttu-id="7cd91-113">このサンプルでは、`IValidateRNIFMessageParts` インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="7cd91-113">The sample implements the `IValidateRNIFMessageParts` interface.</span></span> <span data-ttu-id="7cd91-114">電子メール アドレスが正しい形式でない場合は `RNIFException` が返されます。</span><span class="sxs-lookup"><span data-stu-id="7cd91-114">It returns an `RNIFException` if the e-mail address is not in the correct format.</span></span> <span data-ttu-id="7cd91-115">XML ドキュメント**preambleToValidate**、 **serviceHeaderToValidate**、 **deliveryHeaderToValidate**、および**serviceContentToValidate**検証を定義します。</span><span class="sxs-lookup"><span data-stu-id="7cd91-115">The XML documents **preambleToValidate**, **serviceHeaderToValidate**, **deliveryHeaderToValidate**, and **serviceContentToValidate** define the validation.</span></span>  
  
 <span data-ttu-id="7cd91-116">ValidationAdapter では、RNIFerror.IsOkToSendException プロパティを使用して、エラーが発生した場合に送信するメッセージの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="7cd91-116">The ValidationAdapter uses the RNIFerror.IsOkToSendException property to determine what kind of message to send in the event of an error.</span></span> <span data-ttu-id="7cd91-117">検証に失敗した場合、ValidationAdapter で RNIFerror.ErrorCode がゼロ以外の値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="7cd91-117">If validation does not succeed, the ValidationAdapter sets RNIFerror.ErrorCode to a non-zero value.</span></span> <span data-ttu-id="7cd91-118">RNIFerror.IsOkToSendException プロパティが True の場合は、否定受信確認応答が送信されます。</span><span class="sxs-lookup"><span data-stu-id="7cd91-118">If RNIFerror.IsOkToSendException property is true, the process sends a negative acknowledgment.</span></span> <span data-ttu-id="7cd91-119">RNIF 2.0 では、これは例外メッセージになります。</span><span class="sxs-lookup"><span data-stu-id="7cd91-119">For RNIF 2.0, this is an exception message.</span></span> <span data-ttu-id="7cd91-120">RNIF 1.1 では、これは受信確認例外メッセージになります。</span><span class="sxs-lookup"><span data-stu-id="7cd91-120">For RNIF 1.1, this is a receipt acknowledgment exception message.</span></span> <span data-ttu-id="7cd91-121">RNIFerror.IsOkToSendException プロパティが False で、0A1 が設定されている場合は、0A1 メッセージが送信されます。</span><span class="sxs-lookup"><span data-stu-id="7cd91-121">If RNIFerror.IsOkToSendException property is false and 0A1 is configured, the process will send a 0A1 message.</span></span> <span data-ttu-id="7cd91-122">例外メッセージ、受信確認例外メッセージ、または 0A1 メッセージが送信されると、プロセスは終了します。</span><span class="sxs-lookup"><span data-stu-id="7cd91-122">Once the process sends an exception message, receipt acknowledgment exception message, or 0A1 message, it will terminate.</span></span>  
  
 <span data-ttu-id="7cd91-123">RNIFerror.IsOkToSendException プロパティが False で、0A1 が設定されていない場合は、例外も 0A1 も送信されません。</span><span class="sxs-lookup"><span data-stu-id="7cd91-123">If RNIFerror.IsOkToSendException property is false and 0A1 is not configured, the process will send neither an exception nor a 0A1.</span></span> <span data-ttu-id="7cd91-124">エラーが記録され、プロセスは終了します。</span><span class="sxs-lookup"><span data-stu-id="7cd91-124">It will log the error and then terminate.</span></span>  
  
 <span data-ttu-id="7cd91-125">検証に成功すると、ValidationAdapter で RNIFerror.ErrorCode が 0 に設定され、BTARN によりメッセージがプライベート プロセスにルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="7cd91-125">If validation succeeds, the ValidationAdapter sets RNIFerror.ErrorCode to 0, and BTARN routes the message to the private process.</span></span> <span data-ttu-id="7cd91-126">メッセージがプライベート プロセスにルーティングされるのは、検証が成功した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="7cd91-126">It routes the message to the private process only if validation is successful.</span></span>  
  
## <a name="to-implement-this-sample"></a><span data-ttu-id="7cd91-127">サンプルの実装</span><span class="sxs-lookup"><span data-stu-id="7cd91-127">To Implement this Sample</span></span>  
 <span data-ttu-id="7cd91-128">ValidationAdapter サンプルを実装するには、検証アダプタを引数に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7cd91-128">To implement the ValidationAdapter sample, you must add the validation adapter to the agreement.</span></span>  
  
#### <a name="to-add-the-validation-adapter-to-the-agreement"></a><span data-ttu-id="7cd91-129">検証アダプタをアグリーメントに追加するには</span><span class="sxs-lookup"><span data-stu-id="7cd91-129">To add the validation adapter to the agreement</span></span>  
  
1. <span data-ttu-id="7cd91-130">をクリックして**開始**、 をポイント**すべてのプログラム**、microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]、順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="7cd91-130">Click **Start**, point to **All Programs**, point to Microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2. <span data-ttu-id="7cd91-131">[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、 をクリックし、**契約**します。</span><span class="sxs-lookup"><span data-stu-id="7cd91-131">In the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click **Agreements**.</span></span>  
  
3. <span data-ttu-id="7cd91-132">検証アダプタを追加するアグリーメントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="7cd91-132">Double-click the agreement to which you want to add the validation adapter.</span></span>  
  
4. <span data-ttu-id="7cd91-133">**検証アダプター**  ダイアログ ボックスで、省略記号ボタンをクリックします (**.**) ボタンの右側に**アセンブリ名**、検証アダプタ アセンブリを格納している場所に移動、適切な .dll ファイルを選択およびクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="7cd91-133">In the **Validation Adapter** dialog box, click the ellipsis button (**...**) button to the right of **Assembly name**, move to the location that contains the validation adapter assembly, select the appropriate .dll file, and then click **Open**.</span></span>  
  
5. <span data-ttu-id="7cd91-134">下矢印をクリックして**クラス名**、検証アダプタ クラスを選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="7cd91-134">Click the down arrow for **Class Name**, select the validation adapter class, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cd91-135">参照</span><span class="sxs-lookup"><span data-stu-id="7cd91-135">See Also</span></span>  
 [<span data-ttu-id="7cd91-136">アダプター サンプル</span><span class="sxs-lookup"><span data-stu-id="7cd91-136">Adapter Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)