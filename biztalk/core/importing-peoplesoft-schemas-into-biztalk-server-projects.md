---
title: "BizTalk Server プロジェクトへの PeopleSoft スキーマのインポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas, generating
- schemas, importing into BizTalk Server projects
- component interfaces
- BizTalk Server, schemas [PeopleSoft]
- importing schemas into BizTalk Server
ms.assetid: 411f25f4-4431-44e4-84cf-5c515b3e32db
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4946b438adc0d1e4d360b35207ff69e85b4e2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="importing-peoplesoft-schemas-into-biztalk-server-projects"></a><span data-ttu-id="833d7-102">PeopleSoft スキーマを BizTalk Server プロジェクトにインポートする</span><span class="sxs-lookup"><span data-stu-id="833d7-102">Importing PeopleSoft Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="833d7-103">PeopleSoft Enterprise システムを作成したら、サーバーを参照し、スキーマを BizTalk Server プロジェクトにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="833d7-103">When you have created the PeopleSoft Enterprise system, you can browse the server and import schemas into a BizTalk Server project.</span></span>  
  
## <a name="browsing-a-peoplesoft-server-system"></a><span data-ttu-id="833d7-104">PeopleSoft サーバー システムの参照</span><span class="sxs-lookup"><span data-stu-id="833d7-104">Browsing a PeopleSoft Server System</span></span>  
 <span data-ttu-id="833d7-105">PeopleSoft サーバーを参照するには、アダプター ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="833d7-105">Use the Adapter Wizard to browse a PeopleSoft server.</span></span>  
  
#### <a name="to-browse-a-peoplesoft-server-system"></a><span data-ttu-id="833d7-106">PeopleSoft サーバー システムを参照するには</span><span class="sxs-lookup"><span data-stu-id="833d7-106">To browse a PeopleSoft server system</span></span>  
  
1.  <span data-ttu-id="833d7-107">BizTalk Server プロジェクトを右クリックし、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="833d7-107">Right-click a BizTalk Server project, and select one of the following options.</span></span>  
  
    -   <span data-ttu-id="833d7-108">既に、オブジェクトのスキーマを生成する場合は、選択**追加**をクリックして**スキーマの追加**し、オーケストレーションに追加する既存のスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="833d7-108">If you already have a schema generated for your object, select **Add**, click **Add Schema,** and then select the existing schema to add to your orchestration,.</span></span>  
  
    -   <span data-ttu-id="833d7-109">オンの場合は、オブジェクトのスキーマを生成することはありません、**追加**、順にクリックして**生成した項目の追加**、アダプターを選択します。</span><span class="sxs-lookup"><span data-stu-id="833d7-109">If you do not have a schema generated for your object, select **Add**, then click **Add Generated Items**, and then select the adapter.</span></span> <span data-ttu-id="833d7-110">これは、同じ名前で入力した、 **AdapterProperties**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="833d7-110">This is the same name entered in the **AdapterProperties** dialog box.</span></span> <span data-ttu-id="833d7-111">詳細については、BizTalk のメイン ヘルプで「[アダプターのプロパティ] ダイアログ ボックス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="833d7-111">For more information, see "Adapter Properties Dialog Box" in the main BizTalk help.</span></span>  
  
2.  <span data-ttu-id="833d7-112">[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="833d7-112">Click Next.</span></span>  
  
     <span data-ttu-id="833d7-113">PeopleSoft Enterprise システムがブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="833d7-113">The PeopleSoft Enterprise system appears in the browser.</span></span>  
  
     ![](../core/media/psad-psnewadapter-14-browsing-cominterfacess.gif "PSAd_PSNewAdapter_14_Browsing_ComInterfacess")  
  
### <a name="component-interfaces"></a><span data-ttu-id="833d7-114">コンポーネント インターフェイス</span><span class="sxs-lookup"><span data-stu-id="833d7-114">Component Interfaces</span></span>  
 <span data-ttu-id="833d7-115">**コンポーネント インターフェイス**(CI) フォルダーでは、システムで使用可能なコンポーネントのすべてのインターフェイスを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="833d7-115">In the **Component Interfaces** (CI) folder, you can view all the available component interfaces in the system.</span></span> <span data-ttu-id="833d7-116">コンポーネント インターフェイスでは、サポートされる一連のメソッドとプロパティが宣言されています。</span><span class="sxs-lookup"><span data-stu-id="833d7-116">A component interface declares the set of methods and properties that it supports.</span></span> <span data-ttu-id="833d7-117">動作またはプロパティはコンポーネント インターフェイスでは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="833d7-117">A component interface does not implement behavior or properties.</span></span> <span data-ttu-id="833d7-118">Microsoft BizTalk Adapter for PeopleSoft Enterprise では、CreateEx、DeleteOnly、Find、Get、UpdateEx などの標準メソッドが公開されています。</span><span class="sxs-lookup"><span data-stu-id="833d7-118">Microsoft BizTalk Adapter for PeopleSoft Enterprise exposes standard methods, for example, CreateEx, DeleteOnly, Find, Get, and UpdateEx.</span></span> <span data-ttu-id="833d7-119">これらのメソッドの説明は、次を参照してください。[付録 a: コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)です。</span><span class="sxs-lookup"><span data-stu-id="833d7-119">For a description of these methods, see [Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md).</span></span>  
  
## <a name="generating-schemas"></a><span data-ttu-id="833d7-120">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="833d7-120">Generating Schemas</span></span>  
 <span data-ttu-id="833d7-121">スキーマを生成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="833d7-121">Follow these steps to generate schemas.</span></span>  
  
#### <a name="to-generate-the-schemas"></a><span data-ttu-id="833d7-122">スキーマを生成するには</span><span class="sxs-lookup"><span data-stu-id="833d7-122">To generate the schemas</span></span>  
  
-   <span data-ttu-id="833d7-123">スキーマをインポートする項目を選択します。**メッセージ**、**クエリ**、または**コンポーネント インターフェイス**です。</span><span class="sxs-lookup"><span data-stu-id="833d7-123">Select the item for which you want to import schemas: a **Message**, **Query**, or **Component Interface**.</span></span>  
  
     <span data-ttu-id="833d7-124">選択した項目のスキーマが生成されて、BizTalk Server プロジェクトにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="833d7-124">BizTalk Server generates the schemas for the selected item and imports them into a BizTalk Server project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="833d7-125">サーバー オブジェクトの定義を変更した場合は、スキーマを再生成して、含まれるデータを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="833d7-125">If the server object definitions change, you must regenerate the schema to update the data it contains.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="833d7-126">参照</span><span class="sxs-lookup"><span data-stu-id="833d7-126">See Also</span></span>  
 [<span data-ttu-id="833d7-127">PeopleSoft 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="833d7-127">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)