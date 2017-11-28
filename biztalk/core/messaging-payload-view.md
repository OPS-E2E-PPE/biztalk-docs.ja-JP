---
title: "メッセージング ペイロード ビュー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Messaging Payload view [Tracking Profile Editor]
- message schemas, Tracking Profile Editor
- Tracking Profile Editor, message schemas
- message schemas, payloads
- Tracking Profile Editor, Messaging Payload view
ms.assetid: 2bc247c5-5b31-4cd7-8377-ff9614df1320
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c0ac1c7371bc149e6e132fd810cecf88e31490a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="messaging-payload-view"></a><span data-ttu-id="6470f-102">メッセージング ペイロード ビュー</span><span class="sxs-lookup"><span data-stu-id="6470f-102">Messaging Payload View</span></span>
<span data-ttu-id="6470f-103">メッセージング ペイロード ビューには、選択したアクション (メッセージの送信や受信など) に関連付けられた XML メッセージのスキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6470f-103">The Messaging Payload view displays the schema of the XML message associated with the selected action (for example, Message Sent or Received).</span></span> <span data-ttu-id="6470f-104">このビューは、オーケストレーション スケジュール ビューにある一部の図形のショートカット メニューから使用できます。</span><span class="sxs-lookup"><span data-stu-id="6470f-104">The view is available from the shortcut menu for some of the shapes in the Orchestration Schedule view.</span></span>  
  
## <a name="working-with-the-messaging-payload-view"></a><span data-ttu-id="6470f-105">メッセージング ペイロード ビューの機能</span><span class="sxs-lookup"><span data-stu-id="6470f-105">Working with the Messaging Payload View</span></span>  
 <span data-ttu-id="6470f-106">[イベント ソースの選択] をクリックし、[Select Messaging Payload Schema] をクリックして、オーケストレーション スケジュール ビューを選択します。</span><span class="sxs-lookup"><span data-stu-id="6470f-106">You select your Orchestration Schedule view by clicking the Select Event Source button and clicking the Select Messaging Payload Schema menu item.</span></span> <span data-ttu-id="6470f-107">スキーマを選択すると、このスキーマからアクティビティのデータ項目フォルダーに要素をドラッグできます。つまり、このアクションのメッセージ内の特定の XPath 式からデータを抽出できます。</span><span class="sxs-lookup"><span data-stu-id="6470f-107">Once you select the schema, you can drag elements from this schema to the data item folders of the activity, thus indicating that you want to extract that data from specific XPath expression inside the message at this action.</span></span>  
  
 <span data-ttu-id="6470f-108">メッセージ ペイロードを含む図形を右クリックすると、オーケストレーション スケジュール ビューからメッセージング ペイロード ビューを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="6470f-108">You can open messaging payload views from the orchestration schedule view by right-clicking a shape that contains a message payload.</span></span> <span data-ttu-id="6470f-109">この操作では、コンテキスト メニューが表示されます。[Messaging Payload] をクリックすると、メッセージング プロパティ スキーマを取得できます。</span><span class="sxs-lookup"><span data-stu-id="6470f-109">This will open a context menu from which you can click the Messaging Payload menu item to retrieve the messaging property schema.</span></span>  
  
 <span data-ttu-id="6470f-110">XPath 式の詳細については、次を参照してください。[メッセージ割り当てにおける Xpath の使用](../core/using-xpaths-in-message-assignments.md)です。</span><span class="sxs-lookup"><span data-stu-id="6470f-110">For more information about XPath expressions, see [Using XPaths in Message Assignments](../core/using-xpaths-in-message-assignments.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6470f-111">参照</span><span class="sxs-lookup"><span data-stu-id="6470f-111">See Also</span></span>  
 <span data-ttu-id="6470f-112">[イベント ソース ビューとは何ですか。](../core/what-is-the-source-event-view.md) </span><span class="sxs-lookup"><span data-stu-id="6470f-112">[What Is the Source Event View?](../core/what-is-the-source-event-view.md) </span></span>  
 [<span data-ttu-id="6470f-113">追跡プロファイル エディター</span><span class="sxs-lookup"><span data-stu-id="6470f-113">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)