---
title: シングル サインオン:イベント 10741 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58b6b093-d136-498f-a3b5-c413150da956
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2150f33b90137d5f5e1258a829901426a45d7856
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291734"
---
# <a name="single-sign-on-event-10741"></a><span data-ttu-id="6df10-102">シングル サインオン:イベント 10741</span><span class="sxs-lookup"><span data-stu-id="6df10-102">Single Sign-On: Event 10741</span></span>
## <a name="details"></a><span data-ttu-id="6df10-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6df10-103">Details</span></span>  

|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  <span data-ttu-id="6df10-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6df10-104">Product Name</span></span>   |                                 <span data-ttu-id="6df10-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6df10-105">Enterprise Single Sign-On</span></span>                                 |
| <span data-ttu-id="6df10-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6df10-106">Product Version</span></span> |                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                 |
|    <span data-ttu-id="6df10-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6df10-107">Event ID</span></span>     |                                           <span data-ttu-id="6df10-108">10741</span><span class="sxs-lookup"><span data-stu-id="6df10-108">10741</span></span>                                           |
|  <span data-ttu-id="6df10-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6df10-109">Event Source</span></span>   |                                          <span data-ttu-id="6df10-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6df10-110">ENTSSO</span></span>                                           |
|    <span data-ttu-id="6df10-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6df10-111">Component</span></span>    |                                            <span data-ttu-id="6df10-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="6df10-112">N\A</span></span>                                            |
|  <span data-ttu-id="6df10-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6df10-113">Symbolic Name</span></span>  |                                <span data-ttu-id="6df10-114">SSO_WARN_SAVING_REPLAY_FILE</span><span class="sxs-lookup"><span data-stu-id="6df10-114">SSO_WARN_SAVING_REPLAY_FILE</span></span>                                |
|  <span data-ttu-id="6df10-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6df10-115">Message Text</span></span>   | <span data-ttu-id="6df10-116">再生または進行状況の file.%r を保存しています</span><span class="sxs-lookup"><span data-stu-id="6df10-116">Saving replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="6df10-117">保存したファイル: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="6df10-117">Saved File: %1%r</span></span><br /><br /> <span data-ttu-id="6df10-118">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="6df10-118">Error Code: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="6df10-119">説明</span><span class="sxs-lookup"><span data-stu-id="6df10-119">Explanation</span></span>  
 <span data-ttu-id="6df10-120">この警告イベントは、SSO が再生または進行ファイルを保存することを示します。</span><span class="sxs-lookup"><span data-stu-id="6df10-120">This Warning event indicates that SSO is saving a replay or progress file.</span></span>  

 <span data-ttu-id="6df10-121">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="6df10-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="6df10-122">進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。</span><span class="sxs-lookup"><span data-stu-id="6df10-122">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="6df10-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6df10-123">User Action</span></span>  

- <span data-ttu-id="6df10-124">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6df10-124">No user action is necessary.</span></span>  

  <span data-ttu-id="6df10-125">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6df10-125">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="6df10-126">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="6df10-126">Password Synchronization</span></span>](../core/password-synchronization2.md)
