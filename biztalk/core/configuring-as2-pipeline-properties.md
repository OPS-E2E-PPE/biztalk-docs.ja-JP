---
title: "AS2 パイプラインのプロパティの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.edir2.AS2.pipeline.properties
ms.assetid: 7faf6b05-710a-4d00-8c77-590ce9d9f962
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e41afd99e7af1441e2d3d8cc936c04cd9321779
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-as2-pipeline-properties"></a><span data-ttu-id="59ea4-102">AS2 パイプラインのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="59ea4-102">Configuring AS2 Pipeline Properties</span></span>
<span data-ttu-id="59ea4-103">パイプラインのプロパティは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が送信または受信されたインターチェンジに解決されるアグリーメントを特定できなかった場合に、受信または送信 AS2 メッセージの処理で使用されます。</span><span class="sxs-lookup"><span data-stu-id="59ea4-103">Pipeline properties are used in processing an incoming or outgoing AS2 message when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has not been able to determine the agreement that resolves to the sent or received interchange.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="59ea4-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="59ea4-104">Prerequisites</span></span>  
 <span data-ttu-id="59ea4-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="59ea4-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="as2-pipeline-properties"></a><span data-ttu-id="59ea4-106">AS2 パイプラインのプロパティ</span><span class="sxs-lookup"><span data-stu-id="59ea4-106">AS2 Pipeline Properties</span></span>  
 <span data-ttu-id="59ea4-107">AS2 パイプラインでは、次のプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="59ea4-107">The following property can be set in AS2 pipelines:</span></span>  
  
|<span data-ttu-id="59ea4-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="59ea4-108">Property</span></span>|<span data-ttu-id="59ea4-109">新しく使用する機能</span><span class="sxs-lookup"><span data-stu-id="59ea4-109">Use</span></span>|<span data-ttu-id="59ea4-110">値</span><span class="sxs-lookup"><span data-stu-id="59ea4-110">Values</span></span>|<span data-ttu-id="59ea4-111">パイプライン/ステージ</span><span class="sxs-lookup"><span data-stu-id="59ea4-111">Pipeline/Stage</span></span>|  
|--------------|---------|------------|---------------------|  
|<span data-ttu-id="59ea4-112">ContentTransferEncoding</span><span class="sxs-lookup"><span data-stu-id="59ea4-112">ContentTransferEncoding</span></span>|<span data-ttu-id="59ea4-113">バイナリ データを ASCII テキスト形式で表現するために使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="59ea4-113">Indicates which method will be used for representing binary data in ASCII text format.</span></span>|<span data-ttu-id="59ea4-114">8bit (既定)</span><span class="sxs-lookup"><span data-stu-id="59ea4-114">8bit (default)</span></span><br /><br /> <span data-ttu-id="59ea4-115">7bit</span><span class="sxs-lookup"><span data-stu-id="59ea4-115">7bit</span></span><br /><br /> <span data-ttu-id="59ea4-116">8bit</span><span class="sxs-lookup"><span data-stu-id="59ea4-116">8bit</span></span>|<span data-ttu-id="59ea4-117">AS2EdiSend/エンコード</span><span class="sxs-lookup"><span data-stu-id="59ea4-117">AS2EdiSend/Encode</span></span><br /><br /> <span data-ttu-id="59ea4-118">AS2Send/エンコード</span><span class="sxs-lookup"><span data-stu-id="59ea4-118">AS2Send/Encode</span></span>|  
  
### <a name="to-set-a-pipeline-property"></a><span data-ttu-id="59ea4-119">パイプライン プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="59ea4-119">To set a pipeline property</span></span>  
  
1.  <span data-ttu-id="59ea4-120">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、プロパティを設定するパイプラインを使用している受信場所または送信ポートを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="59ea4-120">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the receive location or send port using the pipeline that you want to set properties for.</span></span> <span data-ttu-id="59ea4-121">**[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59ea4-121">Click **Properties**.</span></span>  
  
2.  <span data-ttu-id="59ea4-122">プロパティを設定する対象のパイプラインの横にある省略記号ボタン ([…]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59ea4-122">Click the ellipsis button (…) next to the pipeline that you want to set properties for.</span></span>  
  
3.  <span data-ttu-id="59ea4-123">プロパティの値を入力し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="59ea4-123">Enter the value for the property, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59ea4-124">参照</span><span class="sxs-lookup"><span data-stu-id="59ea4-124">See Also</span></span>  
 [<span data-ttu-id="59ea4-125">開発と BizTalk Server AS2 ソリューションの構成</span><span class="sxs-lookup"><span data-stu-id="59ea4-125">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)