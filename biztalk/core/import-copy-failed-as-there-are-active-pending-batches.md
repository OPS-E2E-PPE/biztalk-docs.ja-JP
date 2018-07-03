---
title: アクティブな保留中のバッチがあるためインポート コピーできませんでした。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17803f0a-3c70-4a8a-8e8d-7f874ed9ad92
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a74bfdccbd12db00cd0f325aedee2e42cc76729
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970539"
---
# <a name="import-copy-failed-as-there-are-active-pending-batches"></a><span data-ttu-id="17a99-102">アクティブな保留中のバッチがあるためインポート コピーできませんでした。</span><span class="sxs-lookup"><span data-stu-id="17a99-102">Import-Copy failed as there are active-pending batches</span></span>
## <a name="details"></a><span data-ttu-id="17a99-103">詳細</span><span class="sxs-lookup"><span data-stu-id="17a99-103">Details</span></span>  
  
|                 |                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="17a99-104">製品名</span><span class="sxs-lookup"><span data-stu-id="17a99-104">Product Name</span></span>   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| <span data-ttu-id="17a99-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="17a99-105">Product Version</span></span> |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                           |
|    <span data-ttu-id="17a99-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="17a99-106">Event ID</span></span>     |                                                       -                                                        |
|  <span data-ttu-id="17a99-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="17a99-107">Event Source</span></span>   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="17a99-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="17a99-108"> EDI</span></span>             |
|    <span data-ttu-id="17a99-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="17a99-109">Component</span></span>    |                                                   <span data-ttu-id="17a99-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="17a99-110">EDI Engine</span></span>                                                   |
|  <span data-ttu-id="17a99-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="17a99-111">Symbolic Name</span></span>  |                                              <span data-ttu-id="17a99-112">Err_ActiveBatchFound</span><span class="sxs-lookup"><span data-stu-id="17a99-112">Err_ActiveBatchFound</span></span>                                              |
|  <span data-ttu-id="17a99-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="17a99-113">Message Text</span></span>   | <span data-ttu-id="17a99-114">アクティブ状態または保留中のバッチがあるため、インポートまたはコピーはできませんでした</span><span class="sxs-lookup"><span data-stu-id="17a99-114">Import/Copy failed as there are active/pending batches.</span></span> <span data-ttu-id="17a99-115">アクティブ状態または保留中のバッチを停止してから、インポートまたはコピーを再試行してください。</span><span class="sxs-lookup"><span data-stu-id="17a99-115">Stop active/pending batches and try importing/copying.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="17a99-116">説明</span><span class="sxs-lookup"><span data-stu-id="17a99-116">Explanation</span></span>  
 <span data-ttu-id="17a99-117">このエラー/警告/情報イベントは、影響を受けるアグリーメントに 1 つ以上のアクティブ状態または保留中のバッチがあるため、BizTalk Server がバインド ファイルをインポートできなかったか、設定をコピーできなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="17a99-117">This Error/Warning/Information event indicates BizTalk Server was unable to Import a binding file or copy the settings as the affected Agreement(s) have one or more active or pending batch.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="17a99-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="17a99-118">User Action</span></span>  
 <span data-ttu-id="17a99-119">このエラーを解決するには、影響を受けるアグリーメントのすべてのバッチが [アグリーメントのプロパティ] で [停止] と表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="17a99-119">To resolve this error, ensure that all the batches in affected agreements are showing as stopped in the Agreement properties.</span></span>