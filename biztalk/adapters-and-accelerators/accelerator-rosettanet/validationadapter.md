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
ms.openlocfilehash: 0e4c6ba197f12de8236faed0f8494251fe858aeb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299913"
---
# <a name="validationadapter"></a><span data-ttu-id="d8f2a-102">ValidationAdapter</span><span class="sxs-lookup"><span data-stu-id="d8f2a-102">ValidationAdapter</span></span>
<span data-ttu-id="d8f2a-103">ValidationAdapter サンプルは、応答側パブリック プロセス内のメッセージに対して特別な検証ルールを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-103">The ValidationAdapter sample demonstrates how to run special validation rules on a message in a responder public process.</span></span> <span data-ttu-id="d8f2a-104">Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]ネイティブ送信で検証を実行します。 または、受信パイプライン、オーケストレーション内に存在します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-104">Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] natively performs validation in the send or receive pipeline, and in orchestrations.</span></span> <span data-ttu-id="d8f2a-105">追加の検証を実行する場合は、検証アダプターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-105">If you want to perform additional validation, you can create a validation adapter.</span></span> <span data-ttu-id="d8f2a-106">追加の検証には、クロス フィールド検証や、XSD を使用して実装することはできませんビジネス固有の検証規則を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-106">The additional validation could include cross-field validation or business-specific validation rules that you cannot implement using an XSD.</span></span>  
  
 <span data-ttu-id="d8f2a-107">検証アダプターを作成するには追加することで[!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)]ValidationAdapter サンプルで、インターフェイスを公開して、アダプターをアグリーメントのプロパティに入力するコードです。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-107">You can create a validation adapter by adding [!INCLUDE[btsCSharp](../../includes/btscsharp-md.md)] code to the ValidationAdapter sample, publishing the interfaces, and entering the adapter into the agreement properties.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="d8f2a-108">メッセージの処理中に、検証アダプターはし呼び出します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-108">will then call the validation adapter during message processing.</span></span>  
  
 <span data-ttu-id="d8f2a-109">ValidationAdapter は、パブリック プロセス オーケストレーションで使用されるため、そのオーケストレーションをホストしている BizTalk ホスト サービスと同じ資格情報で実行されます。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-109">Since the ValidationAdapter is used by the public process orchestration , it runs under the same credentials as the BizTalk host service hosting that orchestration.</span></span>  
  
 <span data-ttu-id="d8f2a-110">ValidationAdapter サンプルはあります\<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\ValidationAdapter します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-110">The ValidationAdapter sample is located in \<*drive*\>:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\ValidationAdapter.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="d8f2a-111">使用例</span><span class="sxs-lookup"><span data-stu-id="d8f2a-111">Demonstrates</span></span>  
 <span data-ttu-id="d8f2a-112">ValidationAdapter サンプルは、service content の電子メール アドレスの検証を示します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-112">The ValidationAdapter sample demonstrates validation of the e-mail address in the service content.</span></span> <span data-ttu-id="d8f2a-113">サンプルでは実装、`IValidateRNIFMessageParts`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-113">The sample implements the `IValidateRNIFMessageParts` interface.</span></span> <span data-ttu-id="d8f2a-114">返します、`RNIFException`電子メール アドレスが正しい形式でない場合。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-114">It returns an `RNIFException` if the e-mail address is not in the correct format.</span></span> <span data-ttu-id="d8f2a-115">XML ドキュメント**preambleToValidate**、 **serviceHeaderToValidate**、 **deliveryHeaderToValidate**、および**serviceContentToValidate**検証を定義します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-115">The XML documents **preambleToValidate**, **serviceHeaderToValidate**, **deliveryHeaderToValidate**, and **serviceContentToValidate** define the validation.</span></span>  
  
 <span data-ttu-id="d8f2a-116">ValidationAdapter では、RNIFerror.IsOkToSendException プロパティを使用して、エラーが発生した場合に送信するメッセージの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-116">The ValidationAdapter uses the RNIFerror.IsOkToSendException property to determine what kind of message to send in the event of an error.</span></span> <span data-ttu-id="d8f2a-117">検証が成功しなかった場合、ValidationAdapter によって RNIFerror.ErrorCode が 0 以外の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-117">If validation does not succeed, the ValidationAdapter sets RNIFerror.ErrorCode to a non-zero value.</span></span> <span data-ttu-id="d8f2a-118">RNIFerror.IsOkToSendException プロパティが true の場合、プロセスは、否定受信確認応答を送信します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-118">If RNIFerror.IsOkToSendException property is true, the process sends a negative acknowledgment.</span></span> <span data-ttu-id="d8f2a-119">RNIF 2.0 では、これは、例外メッセージです。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-119">For RNIF 2.0, this is an exception message.</span></span> <span data-ttu-id="d8f2a-120">RNIF 1.1 では、これは、受信確認例外メッセージです。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-120">For RNIF 1.1, this is a receipt acknowledgment exception message.</span></span> <span data-ttu-id="d8f2a-121">RNIFerror.IsOkToSendException プロパティが false であり、0A1 が構成されている場合、プロセスは 0A1 メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-121">If RNIFerror.IsOkToSendException property is false and 0A1 is configured, the process will send a 0A1 message.</span></span> <span data-ttu-id="d8f2a-122">例外メッセージ、受信確認例外メッセージ、または 0A1 メッセージを送信すると、プロセスが終了します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-122">Once the process sends an exception message, receipt acknowledgment exception message, or 0A1 message, it will terminate.</span></span>  
  
 <span data-ttu-id="d8f2a-123">RNIFerror.IsOkToSendException プロパティが false であり、0A1 が構成されていない場合、プロセスは、例外も 0A1 に送信されます。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-123">If RNIFerror.IsOkToSendException property is false and 0A1 is not configured, the process will send neither an exception nor a 0A1.</span></span> <span data-ttu-id="d8f2a-124">エラー ログに記録され、終了します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-124">It will log the error and then terminate.</span></span>  
  
 <span data-ttu-id="d8f2a-125">検証が成功すると、ValidationAdapter RNIFerror.ErrorCode を 0 に設定して、BTARN プライベート プロセスにメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-125">If validation succeeds, the ValidationAdapter sets RNIFerror.ErrorCode to 0, and BTARN routes the message to the private process.</span></span> <span data-ttu-id="d8f2a-126">検証が成功した場合にのみ、メッセージをプライベート プロセスにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-126">It routes the message to the private process only if validation is successful.</span></span>  
  
## <a name="to-implement-this-sample"></a><span data-ttu-id="d8f2a-127">このサンプルを実装するには</span><span class="sxs-lookup"><span data-stu-id="d8f2a-127">To Implement this Sample</span></span>  
 <span data-ttu-id="d8f2a-128">ValidationAdapter サンプルを実装するには、契約書に検証アダプターを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-128">To implement the ValidationAdapter sample, you must add the validation adapter to the agreement.</span></span>  
  
#### <a name="to-add-the-validation-adapter-to-the-agreement"></a><span data-ttu-id="d8f2a-129">検証アダプタをアグリーメントに追加するには</span><span class="sxs-lookup"><span data-stu-id="d8f2a-129">To add the validation adapter to the agreement</span></span>  
  
1. <span data-ttu-id="d8f2a-130">をクリックして**開始**、 をポイント**すべてのプログラム**、microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]、順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-130">Click **Start**, point to **All Programs**, point to Microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2. <span data-ttu-id="d8f2a-131">[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、 をクリックし、**契約**します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-131">In the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click **Agreements**.</span></span>  
  
3. <span data-ttu-id="d8f2a-132">検証アダプターを追加するアグリーメントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-132">Double-click the agreement to which you want to add the validation adapter.</span></span>  
  
4. <span data-ttu-id="d8f2a-133">**検証アダプター**  ダイアログ ボックスで、省略記号ボタンをクリックします (**.**) ボタンの右側に**アセンブリ名**、検証アダプタ アセンブリを格納している場所に移動、適切な .dll ファイルを選択およびクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-133">In the **Validation Adapter** dialog box, click the ellipsis button (**...**) button to the right of **Assembly name**, move to the location that contains the validation adapter assembly, select the appropriate .dll file, and then click **Open**.</span></span>  
  
5. <span data-ttu-id="d8f2a-134">下矢印をクリックして**クラス名**、検証アダプタ クラスを選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="d8f2a-134">Click the down arrow for **Class Name**, select the validation adapter class, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f2a-135">参照</span><span class="sxs-lookup"><span data-stu-id="d8f2a-135">See Also</span></span>  
 [<span data-ttu-id="d8f2a-136">アダプター サンプル</span><span class="sxs-lookup"><span data-stu-id="d8f2a-136">Adapter Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)