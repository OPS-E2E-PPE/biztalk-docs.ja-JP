---
title: メッセージング プロパティ ビュー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, message schemas
- message schemas, properties
- Messaging Property view [Tracking Profile Editor]
- Tracking Profile Editor, Messaging Property view
- message schemas, XML messages
ms.assetid: 80d040e9-d58b-41d1-b26d-19aff4d3126b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1be1498cd3766863b9f5b2e3a37ae419d4bafc8a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262898"
---
# <a name="messaging-property-view"></a><span data-ttu-id="757cf-102">メッセージング プロパティ ビュー</span><span class="sxs-lookup"><span data-stu-id="757cf-102">Messaging Property View</span></span>
<span data-ttu-id="757cf-103">メッセージング プロパティ ビューには、プロパティに関連付けられている XML メッセージのスキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="757cf-103">The Messaging Property view displays the schema of the XML message associated with the property.</span></span> <span data-ttu-id="757cf-104">このビューは、オーケストレーション スケジュール ビューにある一部の図形のショートカット メニューから使用できます。</span><span class="sxs-lookup"><span data-stu-id="757cf-104">The view is available from the shortcut menu for some of the shapes in the Orchestration Schedule view.</span></span>  
  
## <a name="working-with-messaging-properties"></a><span data-ttu-id="757cf-105">メッセージング プロパティの操作</span><span class="sxs-lookup"><span data-stu-id="757cf-105">Working with messaging properties</span></span>  
 <span data-ttu-id="757cf-106">クリックして、メッセージング プロパティ ビューを選択する、**イベント ソースの選択**ボタンをクリックしをクリックすると、 **Select Message Property**メニュー項目。</span><span class="sxs-lookup"><span data-stu-id="757cf-106">You select your Messaging Property view by clicking the **Select Event Source** button and clicking the **Select Message Property** menu item.</span></span> <span data-ttu-id="757cf-107">次に、スキーマを選択するメッセージング プロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="757cf-107">You then choose a message property from which to select a schema.</span></span> <span data-ttu-id="757cf-108">スキーマを選択すると、このスキーマからアクティビティのデータ項目フォルダーに要素をドラッグできます。これは、メッセージ内の特定の XPath 式から特定のデータを抽出することを示しています。</span><span class="sxs-lookup"><span data-stu-id="757cf-108">Once you select the schema, you can drag elements from this schema to the data item folders of the activity, thus indicating that you want to extract that particular data from specific XPath expressions inside the message at this action.</span></span>  
  
 <span data-ttu-id="757cf-109">メッセージ ペイロードを含む図形を右クリックすると、オーケストレーション スケジュール ビューからメッセージング プロパティ ビューを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="757cf-109">You can open message property views from the Orchestration Schedule view by right-clicking a shape that contains a message payload.</span></span> <span data-ttu-id="757cf-110">この右クリックで表示されるコンテキスト メニューから、[Message Payload] をクリックすると、図形に関連付けられているペイロードの一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="757cf-110">This will open a context menu from which you can click the Message Payload menu item to retrieve a list of payloads associated with the shape.</span></span>  
  
 <span data-ttu-id="757cf-111">使用できるメッセージング プロパティの一覧は広範にわたることがあります。</span><span class="sxs-lookup"><span data-stu-id="757cf-111">The list of available message properties can be extensive.</span></span> <span data-ttu-id="757cf-112">検索対象のオーケストレーションの名前の一部がわかっている場合でを入力、**文字列**テキスト ボックスをクリック、**検索**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="757cf-112">If you know part of the name of the orchestration for which you are searching, you can type it in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="757cf-113">このように検索すると、入力した文字列を含むメッセージング プロパティのみが選択されます。</span><span class="sxs-lookup"><span data-stu-id="757cf-113">This will select only those message properties that contain the partial string you have entered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="757cf-114">参照</span><span class="sxs-lookup"><span data-stu-id="757cf-114">See Also</span></span>  
 <span data-ttu-id="757cf-115">[イベント ソース ビューとは何ですか。](../core/what-is-the-source-event-view.md) </span><span class="sxs-lookup"><span data-stu-id="757cf-115">[What Is the Source Event View?](../core/what-is-the-source-event-view.md) </span></span>  
 [<span data-ttu-id="757cf-116">追跡プロファイル エディター</span><span class="sxs-lookup"><span data-stu-id="757cf-116">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)