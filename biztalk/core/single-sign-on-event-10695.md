---
title: 'シングル サインオン: イベント 10695 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02c5dc1d-5626-4d24-ac4f-fcd2ae61cd98
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 742d4f802aed2b497a32b20b007c5bac489a8169
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010293"
---
# <a name="single-sign-on-event-10695"></a><span data-ttu-id="d1355-102">シングル サインオン: イベント 10695</span><span class="sxs-lookup"><span data-stu-id="d1355-102">Single Sign-On: Event 10695</span></span>
## <a name="details"></a><span data-ttu-id="d1355-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d1355-103">Details</span></span>  

|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d1355-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d1355-104">Product Name</span></span>   |                                                 <span data-ttu-id="d1355-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d1355-105">Enterprise Single Sign-On</span></span>                                                 |
| <span data-ttu-id="d1355-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d1355-106">Product Version</span></span> |                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                 |
|    <span data-ttu-id="d1355-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d1355-107">Event ID</span></span>     |                                                           <span data-ttu-id="d1355-108">10695</span><span class="sxs-lookup"><span data-stu-id="d1355-108">10695</span></span>                                                           |
|  <span data-ttu-id="d1355-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d1355-109">Event Source</span></span>   |                                                          <span data-ttu-id="d1355-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d1355-110">ENTSSO</span></span>                                                           |
|    <span data-ttu-id="d1355-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d1355-111">Component</span></span>    |                                                            <span data-ttu-id="d1355-112">N\A</span><span class="sxs-lookup"><span data-stu-id="d1355-112">N\A</span></span>                                                            |
|  <span data-ttu-id="d1355-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d1355-113">Symbolic Name</span></span>  |                                           <span data-ttu-id="d1355-114">SSO_ERROR_REPLAY_INCORRECT_FILE_NAME</span><span class="sxs-lookup"><span data-stu-id="d1355-114">SSO_ERROR_REPLAY_INCORRECT_FILE_NAME</span></span>                                            |
|  <span data-ttu-id="d1355-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d1355-115">Message Text</span></span>   | <span data-ttu-id="d1355-116">再生ファイルまたは進行ファイルに破損が検出されました。%r</span><span class="sxs-lookup"><span data-stu-id="d1355-116">Corruption was detected in the replay or progress file.%r</span></span><br /><br /> <span data-ttu-id="d1355-117">ファイル名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d1355-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="d1355-118">ファイル名を復号化: %2</span><span class="sxs-lookup"><span data-stu-id="d1355-118">Decrypted File Name: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="d1355-119">説明</span><span class="sxs-lookup"><span data-stu-id="d1355-119">Explanation</span></span>  
 <span data-ttu-id="d1355-120">このエラー イベントは、SSO が SSO データベースとの接続を再確立したが、破損のために再生ファイルを読み取れなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="d1355-120">This Error event indicates that SSO has re-established contact with the SSO database, but was unable to read the replay file because of corruption.</span></span> <span data-ttu-id="d1355-121">SSO で再生ファイルを開くことができない場合、次の再生ファイルに進みます (次の再生ファイルがある場合)。</span><span class="sxs-lookup"><span data-stu-id="d1355-121">If SSO cannot open a replay file, it will proceed to the next replay file (if there is one).</span></span>  

 <span data-ttu-id="d1355-122">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="d1355-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="d1355-123">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="d1355-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d1355-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d1355-124">User Action</span></span>  
 <span data-ttu-id="d1355-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d1355-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="d1355-126">関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1355-126">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="d1355-127">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="d1355-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="d1355-128">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d1355-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="d1355-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="d1355-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
