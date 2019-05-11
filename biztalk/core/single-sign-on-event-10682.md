---
title: シングル サインオン:イベント 10682 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46f0f425-3946-4bac-a412-488c4afe460d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1a78ed5dcb5897bfcab452285f5fb866fa12030
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397418"
---
# <a name="single-sign-on-event-10682"></a><span data-ttu-id="d27fa-102">シングル サインオン:イベント 10682</span><span class="sxs-lookup"><span data-stu-id="d27fa-102">Single Sign-On: Event 10682</span></span>
## <a name="details"></a><span data-ttu-id="d27fa-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d27fa-103">Details</span></span>  

|                 |                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d27fa-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d27fa-104">Product Name</span></span>   |                                   <span data-ttu-id="d27fa-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d27fa-105">Enterprise Single Sign-On</span></span>                                    |
| <span data-ttu-id="d27fa-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d27fa-106">Product Version</span></span> |                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                   |
|    <span data-ttu-id="d27fa-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d27fa-107">Event ID</span></span>     |                                             <span data-ttu-id="d27fa-108">10682</span><span class="sxs-lookup"><span data-stu-id="d27fa-108">10682</span></span>                                              |
|  <span data-ttu-id="d27fa-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d27fa-109">Event Source</span></span>   |                                             <span data-ttu-id="d27fa-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d27fa-110">ENTSSO</span></span>                                             |
|    <span data-ttu-id="d27fa-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d27fa-111">Component</span></span>    |                                              <span data-ttu-id="d27fa-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="d27fa-112">N\A</span></span>                                               |
|  <span data-ttu-id="d27fa-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d27fa-113">Symbolic Name</span></span>  |                               <span data-ttu-id="d27fa-114">SSO_WARN_REPLAY_INVALID_DIR_FOUND</span><span class="sxs-lookup"><span data-stu-id="d27fa-114">SSO_WARN_REPLAY_INVALID_DIR_FOUND</span></span>                                |
|  <span data-ttu-id="d27fa-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d27fa-115">Message Text</span></span>   | <span data-ttu-id="d27fa-116">ディレクトリが見つかった再生ファイルのディレクトリにされます。 ignored.%r</span><span class="sxs-lookup"><span data-stu-id="d27fa-116">A directory was found in the replay files directory - it will be ignored.%r</span></span><br /><span data-ttu-id="d27fa-117">ディレクトリ: %1</span><span class="sxs-lookup"><span data-stu-id="d27fa-117">Directory: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="d27fa-118">説明</span><span class="sxs-lookup"><span data-stu-id="d27fa-118">Explanation</span></span>  
 <span data-ttu-id="d27fa-119">この警告イベントは、再生ファイルのディレクトリにディレクトリが見つかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="d27fa-119">This Warning event indicates that a directory was found in the replay files directory.</span></span> <span data-ttu-id="d27fa-120">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="d27fa-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="d27fa-121">ここで、パスワードの変更は一時的な暗号化ファイルに格納されも利用できなくなる、SSO データベースに再生されます。</span><span class="sxs-lookup"><span data-stu-id="d27fa-121">In this case the password changes are stored in a temporary encrypted file, and are replayed back to the SSO database when it becomes available again.</span></span> <span data-ttu-id="d27fa-122">再生ファイルのディレクトリは、再生ファイルのみを含める必要があります – ディレクトリが見つかった場合にこのエラー メッセージが発行されます。</span><span class="sxs-lookup"><span data-stu-id="d27fa-122">The replay files directory is expected to contain only replay files – this error message is issued if a directory is found.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d27fa-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d27fa-123">User Action</span></span>  
 <span data-ttu-id="d27fa-124">この警告を解決するには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d27fa-124">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="d27fa-125">コマンド ライン ツール ssoconfig-replayfiles を使用して、再生ディレクトリを変更します。</span><span class="sxs-lookup"><span data-stu-id="d27fa-125">Use command line tool ssoconfig -replayFiles to  change your replay directory.</span></span>  

- <span data-ttu-id="d27fa-126">使用中でない場合は、不適切なディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="d27fa-126">Delete the bad directory if it is not in use.</span></span>  

  <span data-ttu-id="d27fa-127">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="d27fa-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="d27fa-128">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d27fa-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="d27fa-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="d27fa-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
