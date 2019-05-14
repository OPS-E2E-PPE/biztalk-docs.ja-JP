---
title: アダプター メタデータを BizTalk プロジェクトに追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e439e5bf-94b3-4582-bacc-b058e6eb8e17
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f06b60b1dce1b0b9df785d25552f688f7793858
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387309"
---
# <a name="how-to-add-adapter-metadata-to-a-biztalk-project"></a><span data-ttu-id="fe4f6-102">アダプター メタデータを BizTalk プロジェクトに追加する方法</span><span class="sxs-lookup"><span data-stu-id="fe4f6-102">How to Add Adapter Metadata to a BizTalk Project</span></span>
<span data-ttu-id="fe4f6-103">アダプター メタデータの追加ウィザードでは、アダプター メタデータを BizTalk プロジェクトに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-103">The Add Adapter Metadata Wizard enables you to add adapter metadata to a BizTalk project.</span></span> <span data-ttu-id="fe4f6-104">このデータには、スキーマ、メッセージの種類、およびオーケストレーションからアダプターと通信するために必要なポートの種類が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-104">This data includes schemas, message types, and port types needed to communicate with an adapter from an orchestration.</span></span> <span data-ttu-id="fe4f6-105">アダプター メタデータの追加ウィザードを使用して、FTP などのアプリケーション アダプター、システムにこれらのアプリケーション アダプターに対応するプル スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-105">Use the Add Adapter Metadata Wizard with application adapters, such as FTP, to pull schemas corresponding to these application adapters into the system.</span></span> <span data-ttu-id="fe4f6-106">HTTP などのトランスポート アダプターによってスキーマは通常使用しないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-106">Note that transport adapters such as HTTP do not typically use schemas.</span></span>  
  
 <span data-ttu-id="fe4f6-107">次の手順では、アダプターのメタデータを追加する汎用的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-107">The following procedure walks you through the generic steps to add metadata for an adapter.</span></span>  
  
### <a name="to-add-adapter-metadata-to-a-biztalk-project"></a><span data-ttu-id="fe4f6-108">アダプター メタデータを BizTalk プロジェクトに追加するには</span><span class="sxs-lookup"><span data-stu-id="fe4f6-108">To add adapter metadata to a BizTalk project</span></span>  
  
1. <span data-ttu-id="fe4f6-109">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトをソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**追加**、 をクリックし、**生成した項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-109">In your [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, in Solution Explorer, right-click your project, click **Add**, and then click **Add Generated Items**.</span></span>  
  
2. <span data-ttu-id="fe4f6-110">**生成した項目の追加 - \<** <em>プロジェクト名</em>**\>**  ダイアログ ボックスで、**テンプレート** セクションで、選択**アダプターの追加**、 をクリックし、**オープン**。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-110">In the **Add Generated Items - \<**<em>Project name</em>**\>** dialog box, in the **Templates** section, select **Add Adapter**, and then click **Open**.</span></span>  
  
3. <span data-ttu-id="fe4f6-111">アダプター メタデータの追加ウィザードで、**アダプターの選択**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-111">In the Add Adapter Metadata Wizard, on the **Select Adapter** page, do the following.</span></span>  
  
   |<span data-ttu-id="fe4f6-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="fe4f6-112">Use this</span></span>|<span data-ttu-id="fe4f6-113">目的</span><span class="sxs-lookup"><span data-stu-id="fe4f6-113">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="fe4f6-114">アダプターのリスト ボックス</span><span class="sxs-lookup"><span data-stu-id="fe4f6-114">Adapter list box</span></span>|<span data-ttu-id="fe4f6-115">プロジェクトに追加する登録済みのアダプターを選択します。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-115">Select the registered adapter to add to the project.</span></span>|  
   |<span data-ttu-id="fe4f6-116">SQL Server</span><span class="sxs-lookup"><span data-stu-id="fe4f6-116">SQL Server</span></span>|<span data-ttu-id="fe4f6-117">BizTalk データベース サーバー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-117">Enter the BizTalk database server name.</span></span>|  
   |<span data-ttu-id="fe4f6-118">[データベース]</span><span class="sxs-lookup"><span data-stu-id="fe4f6-118">Database</span></span>|<span data-ttu-id="fe4f6-119">選択したサーバーの BizTalk 管理データベースの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-119">Displays the list of BizTalk Management databases for the chosen server.</span></span>|  
   |<span data-ttu-id="fe4f6-120">Port</span><span class="sxs-lookup"><span data-stu-id="fe4f6-120">Port</span></span>|<span data-ttu-id="fe4f6-121">任意。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-121">Optional.</span></span> <span data-ttu-id="fe4f6-122">作成され、BizTalk 管理データベースに格納されているポートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-122">Displays the list of ports created and stored in the BizTalk Management database.</span></span> <span data-ttu-id="fe4f6-123">選択したアダプターを使用するように構成ポートのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-123">Only ports configured to work with the selected adapter are shown.</span></span>|  
  
    <span data-ttu-id="fe4f6-124">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-124">Click **Next**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="fe4f6-125">文字が含まれている生成されたスキーマを追加しようとすると、 **System.XML.XMLConvert**クラスでは、コンパイル エラーの結果をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-125">Attempting to add generated schemas that contain characters that the **System.XML.XMLConvert** class does not support results in a compilation error.</span></span>  
  
4. <span data-ttu-id="fe4f6-126">静的アダプターを使用している場合、 **[インポートするサービス**] ページで、ツリー ビューから利用可能なサービスのセットを選択してクリックして**完了**します。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-126">If you are using a static adapter, on the **Select Services to Import** page, select a set of available services from the tree view, and then click **Finish**.</span></span>  
  
    <span data-ttu-id="fe4f6-127">または、</span><span class="sxs-lookup"><span data-stu-id="fe4f6-127">–Or–</span></span>  
  
    <span data-ttu-id="fe4f6-128">動的アダプターを使用している場合は、ウィザードを完了するカスタム ユーザー インターフェイスの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-128">If you are using a dynamic adapter, follow the steps in the custom user interface to complete the wizard.</span></span>  
  
   <span data-ttu-id="fe4f6-129">ウィザードを完了した後[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーで .odx および .xsd ファイルを示します。</span><span class="sxs-lookup"><span data-stu-id="fe4f6-129">After you complete the wizard, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] lists the .odx and .xsd files in Solution Explorer.</span></span>