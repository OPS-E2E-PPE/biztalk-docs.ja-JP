---
title: コンテキスト プロパティ ビュー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, message schemas
- Context Property view [Tracking Profile Editor]
- Tracking Profile Editor, Context Property view
- message schemas, XML messages
ms.assetid: 17a21b86-995c-4dc2-9a3c-1309837d0b9b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b622c9a82bb199b066dc75b77822a4f0c2e06bdb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390321"
---
# <a name="context-property-view"></a><span data-ttu-id="70f1a-102">コンテキスト プロパティ ビュー</span><span class="sxs-lookup"><span data-stu-id="70f1a-102">Context Property View</span></span>
<span data-ttu-id="70f1a-103">コンテキスト プロパティ ビューには、プロパティに関連付けられた XML メッセージのスキーマが表示されます。</span><span class="sxs-lookup"><span data-stu-id="70f1a-103">The Context Property view displays the schema of the XML message associated with the property.</span></span> <span data-ttu-id="70f1a-104">ビューは、一部の図形 オーケストレーション スケジュール ビューのショートカット メニューから利用できます。</span><span class="sxs-lookup"><span data-stu-id="70f1a-104">The view is available from the shortcut menu for some of the shapes in the Orchestration Schedule view.</span></span>  
  
## <a name="working-with-the-context-property-view"></a><span data-ttu-id="70f1a-105">コンテキスト プロパティ ビューの操作</span><span class="sxs-lookup"><span data-stu-id="70f1a-105">Working with the Context Property view</span></span>  
 <span data-ttu-id="70f1a-106">クリックして、コンテキスト プロパティ ビューを選択、**イベント ソースの選択**クリックし、 **コンテキスト プロパティの**メニュー項目。</span><span class="sxs-lookup"><span data-stu-id="70f1a-106">You select your Context Property view by clicking the **Select Event Source** button and clicking the **Select Context Property** menu item.</span></span> <span data-ttu-id="70f1a-107">コンテキスト プロパティは、そのプロパティのスキーマを読み込むの既知のコンテキスト プロパティの一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="70f1a-107">You then choose a context property from the list of known context properties to load the schema for that property.</span></span> <span data-ttu-id="70f1a-108">プロパティを選択するとする要素をドラッグできます、関連付けられたスキーマからアクティビティのデータ項目フォルダーにこのアクションのメッセージ内の特定の XPath 式からそのデータを抽出することを示します。</span><span class="sxs-lookup"><span data-stu-id="70f1a-108">Once you select the property, you can drag elements from the associated schema to the data item folders of the activity, thus indicating you want to extract that data from specific XPath expression inside the message at this action.</span></span>  
  
 <span data-ttu-id="70f1a-109">オーケストレーション スケジュール ビューからコンテキスト プロパティ ビューを開くには、コンテキスト プロパティを含む図形を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="70f1a-109">You can open context property views from the orchestration schedule view by right-clicking a shape that contains a context property.</span></span> <span data-ttu-id="70f1a-110">クリックする、コンテキスト メニューが開きます、**コンテキスト プロパティ スキーマ**図形に関連付けられているコンテキスト プロパティの一覧を取得するメニュー項目。</span><span class="sxs-lookup"><span data-stu-id="70f1a-110">This will open a context menu from which you can click the **Context Property Schema** menu item to retrieve a list of context properties associated with the shape.</span></span>  
  
 <span data-ttu-id="70f1a-111">使用可能なコンテキスト プロパティの一覧は広範にすることはできます。</span><span class="sxs-lookup"><span data-stu-id="70f1a-111">The list of available context properties can be extensive.</span></span> <span data-ttu-id="70f1a-112">検索対象のプロパティの名前の一部がわかっている場合でを入力、**文字列**テキスト ボックスをクリックして、**検索**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="70f1a-112">If you know part of the name of the property for which you are searching, you can type it in the **In String** text box and click the **Search** button.</span></span> <span data-ttu-id="70f1a-113">これにより、入力した部分文字列を含むプロパティのみが選択されます。</span><span class="sxs-lookup"><span data-stu-id="70f1a-113">This will select only those properties that contain the partial string you have entered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70f1a-114">コンテキスト プロパティ ビューからマップを選択すると、潜在的なプロパティ スキーマの一覧は、BizTalk Server のインストールで構成されているすべてのプロパティ スキーマの完全な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="70f1a-114">When you choose to map from the Context Properties view, the list of potential property schemas is a complete list of every property schema configured in your BizTalk Server installation.</span></span>  <span data-ttu-id="70f1a-115">必要なスキーマの表示が機密性の高い、BizTalk Server の機能は、作業している実行中のプロセスによって使用されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="70f1a-115">You must aware that the schemas presented are not sensitive to which features in BizTalk Server are used by the running process on which you are working.</span></span> <span data-ttu-id="70f1a-116">たとえば、マッピング、コンテキスト プロパティからすると、スキーマの一覧からの SOAP プロパティ スキーマを選択することができますが、実行中のプロセスは、SOAP を使用しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="70f1a-116">For example, you can select a schema for SOAP properties from the list of schemas offered when mapping from Context Properties, but the running process itself may not use SOAP.</span></span> <span data-ttu-id="70f1a-117">BAM によってキャプチャされているデータを null または空で、未使用のプロパティの結果からマップされた BAM アクティビティ項目。</span><span class="sxs-lookup"><span data-stu-id="70f1a-117">Any BAM activity item mapped from an unused property results in null or empty data being captured by BAM.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f1a-118">参照</span><span class="sxs-lookup"><span data-stu-id="70f1a-118">See Also</span></span>  
 <span data-ttu-id="70f1a-119">[イベント ソース ビューとは何ですか。](../core/what-is-the-source-event-view.md) </span><span class="sxs-lookup"><span data-stu-id="70f1a-119">[What Is the Source Event View?](../core/what-is-the-source-event-view.md) </span></span>  
 [<span data-ttu-id="70f1a-120">追跡プロファイル エディター</span><span class="sxs-lookup"><span data-stu-id="70f1a-120">Tracking Profile Editor</span></span>](../core/tracking-profile-editor.md)