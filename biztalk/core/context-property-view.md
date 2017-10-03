---
title: "コンテキスト プロパティ ビュー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, message schemas
- Context Property view [Tracking Profile Editor]
- Tracking Profile Editor, Context Property view
- message schemas, XML messages
ms.assetid: 17a21b86-995c-4dc2-9a3c-1309837d0b9b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84a0f3a1d507e1440f67cd5f9e4afa18bff0b52a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="context-property-view"></a><span data-ttu-id="84b70-102">コンテキスト プロパティ ビュー</span><span class="sxs-lookup"><span data-stu-id="84b70-102">Context Property View</span></span>
<span data-ttu-id="84b70-103">コンテキスト プロパティ ビューには、プロパティと関連付けられている XML メッセージのスキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="84b70-103">The Context Property view displays the schema of the XML message associated with the property.</span></span> <span data-ttu-id="84b70-104">このビューは、オーケストレーション スケジュール ビューにある一部の図形のショートカット メニューから使用できます。</span><span class="sxs-lookup"><span data-stu-id="84b70-104">The view is available from the shortcut menu for some of the shapes in the Orchestration Schedule view.</span></span>  
  
## <a name="working-with-the-context-property-view"></a><span data-ttu-id="84b70-105">コンテキスト プロパティ ビューの操作</span><span class="sxs-lookup"><span data-stu-id="84b70-105">Working with the Context Property view</span></span>  
 <span data-ttu-id="84b70-106">クリックして、コンテキスト プロパティ ビューを選択する、**イベント ソースの選択**ボタンをクリックしをクリックすると、 **コンテキスト プロパティの**メニュー項目。</span><span class="sxs-lookup"><span data-stu-id="84b70-106">You select your Context Property view by clicking the **Select Event Source** button and clicking the **Select Context Property** menu item.</span></span> <span data-ttu-id="84b70-107">次に、既知のコンテキスト プロパティの一覧からコンテキスト プロパティを選択し、そのプロパティのスキーマを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="84b70-107">You then choose a context property from the list of known context properties to load the schema for that property.</span></span> <span data-ttu-id="84b70-108">プロパティを選択すると、関連付けられたスキーマからアクティビティのデータ項目フォルダーに要素をドラッグできます。つまり、このアクションのメッセージ内の特定の XPath 式からデータを抽出できます。</span><span class="sxs-lookup"><span data-stu-id="84b70-108">Once you select the property, you can drag elements from the associated schema to the data item folders of the activity, thus indicating you want to extract that data from specific XPath expression inside the message at this action.</span></span>  
  
 <span data-ttu-id="84b70-109">コンテキスト プロパティを含む図形を右クリックすると、オーケストレーション スケジュール ビューからコンテキスト プロパティ ビューを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="84b70-109">You can open context property views from the orchestration schedule view by right-clicking a shape that contains a context property.</span></span> <span data-ttu-id="84b70-110">クリックしてコンテキスト メニューが開き、この、**コンテキスト プロパティ スキーマ**図形に関連付けられているコンテキスト プロパティの一覧を取得するメニュー項目。</span><span class="sxs-lookup"><span data-stu-id="84b70-110">This will open a context menu from which you can click the **Context Property Schema** menu item to retrieve a list of context properties associated with the shape.</span></span>  
  
 <span data-ttu-id="84b70-111">このコンテキスト プロパティの一覧には、使用可能なプロパティが非常に多く表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="84b70-111">The list of available context properties can be extensive.</span></span> <span data-ttu-id="84b70-112">検索対象のプロパティの名前の一部がわかっている場合でを入力、**文字列**テキスト ボックスをクリック、**検索**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="84b70-112">If you know part of the name of the property for which you are searching, you can type it in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="84b70-113">これにより、入力した文字列を含むプロパティのみが選択され、表示されます。</span><span class="sxs-lookup"><span data-stu-id="84b70-113">This will select only those properties that contain the partial string you have entered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84b70-114">コンテキスト プロパティ ビューからマップする場合、プロパティ スキーマの一覧には、BizTalk Server で構成されているすべてのプロパティ スキーマが含まれます。</span><span class="sxs-lookup"><span data-stu-id="84b70-114">When you choose to map from the Context Properties view, the list of potential property schemas is a complete list of every property schema configured in your BizTalk Server installation.</span></span>  <span data-ttu-id="84b70-115">一覧に表示されたスキーマは、操作している BizTalk Server のプロセスで使用されている機能とは対応していません。</span><span class="sxs-lookup"><span data-stu-id="84b70-115">You must aware that the schemas presented are not sensitive to which features in BizTalk Server are used by the running process on which you are working.</span></span> <span data-ttu-id="84b70-116">たとえば、実行中のプロセスで SOAP が使用されていなくても、コンテキスト プロパティからマップすると、スキーマの一覧から SOAP プロパティのスキーマを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="84b70-116">For example, you can select a schema for SOAP properties from the list of schemas offered when mapping from Context Properties, but the running process itself may not use SOAP.</span></span> <span data-ttu-id="84b70-117">未使用のプロパティからマップされた BAM アクティビティ項目は、BAM では NULL または空のデータとしてキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="84b70-117">Any BAM activity item mapped from an unused property results in null or empty data being captured by BAM.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84b70-118">参照</span><span class="sxs-lookup"><span data-stu-id="84b70-118">See Also</span></span>  
 <span data-ttu-id="84b70-119">[イベント ソース ビューとは何ですか。](../core/what-is-the-source-event-view.md) </span><span class="sxs-lookup"><span data-stu-id="84b70-119">[What Is the Source Event View?](../core/what-is-the-source-event-view.md) </span></span>  
 [<span data-ttu-id="84b70-120">追跡プロファイル エディター</span><span class="sxs-lookup"><span data-stu-id="84b70-120">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)