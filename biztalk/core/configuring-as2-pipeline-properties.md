---
title: AS2 パイプラインのプロパティの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edir2.AS2.pipeline.properties
ms.assetid: 7faf6b05-710a-4d00-8c77-590ce9d9f962
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d2bb679e4e150382cd8ff3e80c838d269ba908f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988875"
---
# <a name="configuring-as2-pipeline-properties"></a><span data-ttu-id="cd7f2-102">AS2 パイプラインのプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="cd7f2-102">Configuring AS2 Pipeline Properties</span></span>
<span data-ttu-id="cd7f2-103">パイプラインのプロパティは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が送信または受信されたインターチェンジに解決されるアグリーメントを特定できなかった場合に、受信または送信 AS2 メッセージの処理で使用されます。</span><span class="sxs-lookup"><span data-stu-id="cd7f2-103">Pipeline properties are used in processing an incoming or outgoing AS2 message when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has not been able to determine the agreement that resolves to the sent or received interchange.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cd7f2-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="cd7f2-104">Prerequisites</span></span>  
 <span data-ttu-id="cd7f2-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd7f2-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="as2-pipeline-properties"></a><span data-ttu-id="cd7f2-106">AS2 パイプラインのプロパティ</span><span class="sxs-lookup"><span data-stu-id="cd7f2-106">AS2 Pipeline Properties</span></span>  
 <span data-ttu-id="cd7f2-107">AS2 パイプラインでは、次のプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="cd7f2-107">The following property can be set in AS2 pipelines:</span></span>  
  
|<span data-ttu-id="cd7f2-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cd7f2-108">Property</span></span>|<span data-ttu-id="cd7f2-109">新しく使用する機能</span><span class="sxs-lookup"><span data-stu-id="cd7f2-109">Use</span></span>|<span data-ttu-id="cd7f2-110">値</span><span class="sxs-lookup"><span data-stu-id="cd7f2-110">Values</span></span>|<span data-ttu-id="cd7f2-111">パイプライン/ステージ</span><span class="sxs-lookup"><span data-stu-id="cd7f2-111">Pipeline/Stage</span></span>|  
|--------------|---------|------------|---------------------|  
|<span data-ttu-id="cd7f2-112">ContentTransferEncoding</span><span class="sxs-lookup"><span data-stu-id="cd7f2-112">ContentTransferEncoding</span></span>|<span data-ttu-id="cd7f2-113">バイナリ データを ASCII テキスト形式で表現するために使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cd7f2-113">Indicates which method will be used for representing binary data in ASCII text format.</span></span>|<span data-ttu-id="cd7f2-114">8bit (既定)</span><span class="sxs-lookup"><span data-stu-id="cd7f2-114">8bit (default)</span></span><br /><br /> <span data-ttu-id="cd7f2-115">7bit</span><span class="sxs-lookup"><span data-stu-id="cd7f2-115">7bit</span></span><br /><br /> <span data-ttu-id="cd7f2-116">8bit</span><span class="sxs-lookup"><span data-stu-id="cd7f2-116">8bit</span></span>|<span data-ttu-id="cd7f2-117">AS2EdiSend/エンコード</span><span class="sxs-lookup"><span data-stu-id="cd7f2-117">AS2EdiSend/Encode</span></span><br /><br /> <span data-ttu-id="cd7f2-118">AS2Send/エンコード</span><span class="sxs-lookup"><span data-stu-id="cd7f2-118">AS2Send/Encode</span></span>|  
  
### <a name="to-set-a-pipeline-property"></a><span data-ttu-id="cd7f2-119">パイプライン プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="cd7f2-119">To set a pipeline property</span></span>  
  
1. <span data-ttu-id="cd7f2-120">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、プロパティを設定するパイプラインを使用している受信場所または送信ポートを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="cd7f2-120">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the receive location or send port using the pipeline that you want to set properties for.</span></span> <span data-ttu-id="cd7f2-121">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd7f2-121">Click **Properties**.</span></span>  
  
2. <span data-ttu-id="cd7f2-122">プロパティを設定する対象のパイプラインの横にある省略記号ボタン ([…]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cd7f2-122">Click the ellipsis button (…) next to the pipeline that you want to set properties for.</span></span>  
  
3. <span data-ttu-id="cd7f2-123">プロパティの値を入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="cd7f2-123">Enter the value for the property, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd7f2-124">参照</span><span class="sxs-lookup"><span data-stu-id="cd7f2-124">See Also</span></span>  
 [<span data-ttu-id="cd7f2-125">BizTalk Server AS2 ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="cd7f2-125">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)