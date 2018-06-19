---
title: スキーマ Validation2 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f9d1576-10df-4c5a-9ae0-618f0dd54b4e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 317fa8e0e5e557993922bba383ebf5eca460fa69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269242"
---
# <a name="schema-validation"></a><span data-ttu-id="60f8a-102">スキーマの検証</span><span class="sxs-lookup"><span data-stu-id="60f8a-102">Schema Validation</span></span>
<span data-ttu-id="60f8a-103">EDI 受信パイプラインと EDI 送信パイプラインは、次のスキーマを使用してメッセージを検証します。</span><span class="sxs-lookup"><span data-stu-id="60f8a-103">The EDI receive pipeline and EDI send pipeline validate a message using the following schemas:</span></span>  
  
-   <span data-ttu-id="60f8a-104">**エンベロープの検証**: サービス スキーマを`Microsoft.BizTalk.Edi.BaseArtifacts.dll`で[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60f8a-104">**Envelope validation**: Service schema in `Microsoft.BizTalk.Edi.BaseArtifacts.dll` in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]</span></span>  
  
-   <span data-ttu-id="60f8a-105">**トランザクション セットの検証**: に、スキーマ内のメッセージ スキーマを格納[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]xsd_schema \edi</span><span class="sxs-lookup"><span data-stu-id="60f8a-105">**Transaction set validation**: Message schemas in the schema store in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI</span></span>  
  
-   <span data-ttu-id="60f8a-106">**受信確認メッセージの検証**: CONTRL、997、および TA1 のスキーマ`Microsoft.BizTalk.Edi.BaseArtifacts.dll`です。</span><span class="sxs-lookup"><span data-stu-id="60f8a-106">**Acknowledgment message validation**: CONTRL, 997, and TA1 schema in `Microsoft.BizTalk.Edi.BaseArtifacts.dll`.</span></span>  
  
 <span data-ttu-id="60f8a-107">`Microsoft.BizTalk.Edi.BaseArtifacts.dll` 内のスキーマは、セットアップ プログラムによって自動的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="60f8a-107">The schemas in `Microsoft.BizTalk.Edi.BaseArtifacts.dll` are automatically deployed by the setup program.</span></span> <span data-ttu-id="60f8a-108">これらのスキーマは、「、**スキーマ**のノード、 **BizTalk EDI アプリケーション**で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="60f8a-108">These schemas are listed in the **Schemas** node of the **BizTalk EDI Application** in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="60f8a-109">メッセージ スキーマを使用するには、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI フォルダー内の MicrosoftEdiXSDTemplates.exe 自己解凍ファイルを実行してサーバーのハード ドライブにスキーマをインストールし、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でそのスキーマをプロジェクトに展開します。</span><span class="sxs-lookup"><span data-stu-id="60f8a-109">To use the message schemas, you must install them on the hard drive of your server by executing the MicrosoftEdiXSDTemplates.exe self-extracting file in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder, and then deploy them in your project in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="60f8a-110">**スキーマの決定**</span><span class="sxs-lookup"><span data-stu-id="60f8a-110">**Schema Determination**</span></span>  
  
 <span data-ttu-id="60f8a-111">EDI 受信パイプラインは、受信メッセージの処理時に、アグリーメントの参照とスキーマ検索プロセスを実行して、メッセージの処理に使用するスキーマの名前空間を決定します。</span><span class="sxs-lookup"><span data-stu-id="60f8a-111">When the EDI receive pipeline processes a receive message, it determines the namespace of the schema to use in processing the message through the agreement lookup and schema discovery process.</span></span> <span data-ttu-id="60f8a-112">詳細については、次を参照してください。[アグリーメントの解決、スキーマ探索、および受信した EDI メッセージの承認](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)です。</span><span class="sxs-lookup"><span data-stu-id="60f8a-112">For more information, see [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
 <span data-ttu-id="60f8a-113">EDI 送信パイプラインは、送信メッセージの作成時に、アグリーメント プロパティを使用してエンベロープに必要事項を記載した後、トランザクション セット内の情報に対してスキーマの検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="60f8a-113">When the EDI send pipeline creates a message to send, it uses agreement properties to populate the envelope, and then performs schema validation of the information in the transaction set.</span></span> <span data-ttu-id="60f8a-114">スキーマが読み込まれると、送信パイプラインは、スキーマをアグリーメント プロパティ (アグリーメントが指定されていない場合はフォールバック アグリーメント) に照らし合わせて検証します。</span><span class="sxs-lookup"><span data-stu-id="60f8a-114">After loading the schema, the send pipeline validates the schema against agreement properties (or fallback agreement if no agreement has been designated).</span></span> <span data-ttu-id="60f8a-115">スキーマの検証に成功したら、パイプラインは、そのスキーマに照らし合わせてトランザクション セットを検証します。</span><span class="sxs-lookup"><span data-stu-id="60f8a-115">If the schema validates, the pipeline validates the transaction set against the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f8a-116">参照</span><span class="sxs-lookup"><span data-stu-id="60f8a-116">See Also</span></span>  
 [<span data-ttu-id="60f8a-117">EDI メッセージの検証</span><span class="sxs-lookup"><span data-stu-id="60f8a-117">EDI Message Validation</span></span>](../core/edi-message-validation.md)