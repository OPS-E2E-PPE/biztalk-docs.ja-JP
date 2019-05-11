---
title: PeopleSoft スキーマを Visual Studio にインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 411f25f4-4431-44e4-84cf-5c515b3e32db
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89534c67d772f8b025289d61ab515f1585791d68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382481"
---
# <a name="import-peoplesoft-schemas-into-biztalk-server-projects"></a><span data-ttu-id="8b39c-102">PeopleSoft スキーマを BizTalk Server プロジェクトにインポートします。</span><span class="sxs-lookup"><span data-stu-id="8b39c-102">Import PeopleSoft Schemas into BizTalk Server Projects</span></span>
<span data-ttu-id="8b39c-103">PeopleSoft Enterprise システムを作成したら、サーバーを参照し、BizTalk Server プロジェクトにスキーマをインポートできます。</span><span class="sxs-lookup"><span data-stu-id="8b39c-103">When you have created the PeopleSoft Enterprise system, you can browse the server and import schemas into a BizTalk Server project.</span></span>  
  
## <a name="browse-a-peoplesoft-server-system"></a><span data-ttu-id="8b39c-104">PeopleSoft サーバー システムを参照します。</span><span class="sxs-lookup"><span data-stu-id="8b39c-104">Browse a PeopleSoft Server System</span></span>  
  
1.  <span data-ttu-id="8b39c-105">BizTalk Server プロジェクトを右クリックし、次のオプションのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="8b39c-105">Right-click a BizTalk Server project, and select one of the following options.</span></span>  
  
    -   <span data-ttu-id="8b39c-106">既に、オブジェクトのスキーマを生成する場合は、選択**追加**、 をクリックして**スキーマの追加、** し、オーケストレーションに追加する既存のスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="8b39c-106">If you already have a schema generated for your object, select **Add**, click **Add Schema,** and then select the existing schema to add to your orchestration,.</span></span>  
  
    -   <span data-ttu-id="8b39c-107">オブジェクトのスキーマを生成しない場合は、選択**追加**、 をクリックし、**生成した項目の追加**、アダプターを選択します。</span><span class="sxs-lookup"><span data-stu-id="8b39c-107">If you do not have a schema generated for your object, select **Add**, then click **Add Generated Items**, and then select the adapter.</span></span> <span data-ttu-id="8b39c-108">これは、同じ名前で入力、 **AdapterProperties**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8b39c-108">This is the same name entered in the **AdapterProperties** dialog box.</span></span> <span data-ttu-id="8b39c-109">詳細については、BizTalk のメイン ヘルプで「アダプターのプロパティ ダイアログ ボックス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b39c-109">For more information, see "Adapter Properties Dialog Box" in the main BizTalk help.</span></span>  
  
2.  <span data-ttu-id="8b39c-110">[次へ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8b39c-110">Click Next.</span></span>  
  
     <span data-ttu-id="8b39c-111">PeopleSoft Enterprise システムは、ブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b39c-111">The PeopleSoft Enterprise system appears in the browser.</span></span>  
  
     <span data-ttu-id="8b39c-112">![](../core/media/psad-psnewadapter-14-browsing-cominterfacess.gif "PSAd_PSNewAdapter_14_Browsing_ComInterfacess")</span><span class="sxs-lookup"><span data-stu-id="8b39c-112">![](../core/media/psad-psnewadapter-14-browsing-cominterfacess.gif "PSAd_PSNewAdapter_14_Browsing_ComInterfacess")</span></span>  
  
### <a name="component-interfaces"></a><span data-ttu-id="8b39c-113">コンポーネント インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b39c-113">Component Interfaces</span></span>  
 <span data-ttu-id="8b39c-114">**コンポーネント インターフェイス**(CI) フォルダー、システムですべての利用可能なコンポーネント インターフェイスを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="8b39c-114">In the **Component Interfaces** (CI) folder, you can view all the available component interfaces in the system.</span></span> <span data-ttu-id="8b39c-115">コンポーネント インターフェイスでは、メソッドとサポートされるプロパティのセットを宣言します。</span><span class="sxs-lookup"><span data-stu-id="8b39c-115">A component interface declares the set of methods and properties that it supports.</span></span> <span data-ttu-id="8b39c-116">コンポーネント インターフェイスは、動作またはプロパティを実装していません。</span><span class="sxs-lookup"><span data-stu-id="8b39c-116">A component interface does not implement behavior or properties.</span></span> <span data-ttu-id="8b39c-117">Microsoft BizTalk Adapter for PeopleSoft Enterprise では、たとえば、CreateEx、DeleteOnly、Find、Get、および UpdateEx、標準的なメソッドを公開します。</span><span class="sxs-lookup"><span data-stu-id="8b39c-117">Microsoft BizTalk Adapter for PeopleSoft Enterprise exposes standard methods, for example, CreateEx, DeleteOnly, Find, Get, and UpdateEx.</span></span> <span data-ttu-id="8b39c-118">これらのメソッドの説明は、次を参照してください[付録 a:。コンポーネント インターフェイス メソッド](../core/appendix-a-component-interface-methods.md)します。</span><span class="sxs-lookup"><span data-stu-id="8b39c-118">For a description of these methods, see [Appendix A: Component Interface Methods](../core/appendix-a-component-interface-methods.md).</span></span>  
  
## <a name="generate-schemas"></a><span data-ttu-id="8b39c-119">スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="8b39c-119">Generate Schemas</span></span>  
  
<span data-ttu-id="8b39c-120">スキーマをインポートする項目を選択します。**メッセージ**、**クエリ**、または**コンポーネント インターフェイス**します。</span><span class="sxs-lookup"><span data-stu-id="8b39c-120">Select the item for which you want to import schemas: a **Message**, **Query**, or **Component Interface**.</span></span>  <span data-ttu-id="8b39c-121">BizTalk Server では、選択した項目のスキーマが生成され、BizTalk Server プロジェクトにインポートします。</span><span class="sxs-lookup"><span data-stu-id="8b39c-121">BizTalk Server generates the schemas for the selected item and imports them into a BizTalk Server project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b39c-122">サーバー オブジェクトの定義を変更する場合が含まれているデータを更新するスキーマを再生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b39c-122">If the server object definitions change, you must regenerate the schema to update the data it contains.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b39c-123">参照</span><span class="sxs-lookup"><span data-stu-id="8b39c-123">See Also</span></span>  
 [<span data-ttu-id="8b39c-124">PeopleSoft 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="8b39c-124">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)