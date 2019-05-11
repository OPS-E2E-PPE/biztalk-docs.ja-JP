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
ms.openlocfilehash: 7b8168af5ba8d9fbb242833011bfb0d9a51bdd96
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391353"
---
# <a name="configuring-as2-pipeline-properties"></a><span data-ttu-id="4cc52-102">AS2 パイプラインのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="4cc52-102">Configuring AS2 Pipeline Properties</span></span>
<span data-ttu-id="4cc52-103">パイプラインのプロパティは、受信または送信の AS2 の処理で使用メッセージ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信または受信したインターチェンジに解決されるアグリーメントを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="4cc52-103">Pipeline properties are used in processing an incoming or outgoing AS2 message when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] has not been able to determine the agreement that resolves to the sent or received interchange.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4cc52-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="4cc52-104">Prerequisites</span></span>  
 <span data-ttu-id="4cc52-105">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4cc52-105">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="as2-pipeline-properties"></a><span data-ttu-id="4cc52-106">AS2 パイプラインのプロパティ</span><span class="sxs-lookup"><span data-stu-id="4cc52-106">AS2 Pipeline Properties</span></span>  
 <span data-ttu-id="4cc52-107">AS2 パイプラインでは、次のプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="4cc52-107">The following property can be set in AS2 pipelines:</span></span>  
  
|<span data-ttu-id="4cc52-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4cc52-108">Property</span></span>|<span data-ttu-id="4cc52-109">新しく使用する機能</span><span class="sxs-lookup"><span data-stu-id="4cc52-109">Use</span></span>|<span data-ttu-id="4cc52-110">値</span><span class="sxs-lookup"><span data-stu-id="4cc52-110">Values</span></span>|<span data-ttu-id="4cc52-111">パイプライン/ステージ</span><span class="sxs-lookup"><span data-stu-id="4cc52-111">Pipeline/Stage</span></span>|  
|--------------|---------|------------|---------------------|  
|<span data-ttu-id="4cc52-112">ContentTransferEncoding</span><span class="sxs-lookup"><span data-stu-id="4cc52-112">ContentTransferEncoding</span></span>|<span data-ttu-id="4cc52-113">ASCII テキスト形式でバイナリ データを表現するメソッドが使用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="4cc52-113">Indicates which method will be used for representing binary data in ASCII text format.</span></span>|<span data-ttu-id="4cc52-114">8 bit (既定値)</span><span class="sxs-lookup"><span data-stu-id="4cc52-114">8bit (default)</span></span><br /><br /> <span data-ttu-id="4cc52-115">7 ビット</span><span class="sxs-lookup"><span data-stu-id="4cc52-115">7bit</span></span><br /><br /> <span data-ttu-id="4cc52-116">8 ビット</span><span class="sxs-lookup"><span data-stu-id="4cc52-116">8bit</span></span>|<span data-ttu-id="4cc52-117">AS2EdiSend/エンコード</span><span class="sxs-lookup"><span data-stu-id="4cc52-117">AS2EdiSend/Encode</span></span><br /><br /> <span data-ttu-id="4cc52-118">AS2Send/エンコード</span><span class="sxs-lookup"><span data-stu-id="4cc52-118">AS2Send/Encode</span></span>|  
  
### <a name="to-set-a-pipeline-property"></a><span data-ttu-id="4cc52-119">パイプライン プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="4cc52-119">To set a pipeline property</span></span>  
  
1. <span data-ttu-id="4cc52-120">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、受信場所を右クリックするか送信ポートのプロパティを設定するパイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="4cc52-120">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the receive location or send port using the pipeline that you want to set properties for.</span></span> <span data-ttu-id="4cc52-121">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc52-121">Click **Properties**.</span></span>  
  
2. <span data-ttu-id="4cc52-122">プロパティを設定する対象のパイプラインの横にある省略記号ボタン ([…]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4cc52-122">Click the ellipsis button (…) next to the pipeline that you want to set properties for.</span></span>  
  
3. <span data-ttu-id="4cc52-123">プロパティの値を入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4cc52-123">Enter the value for the property, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc52-124">参照</span><span class="sxs-lookup"><span data-stu-id="4cc52-124">See Also</span></span>  
 [<span data-ttu-id="4cc52-125">BizTalk Server AS2 ソリューションの開発と構成</span><span class="sxs-lookup"><span data-stu-id="4cc52-125">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)