---
title: シングル サインオン:イベント 10727 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ff7ac94-6f1e-4e56-853e-efc50b1fa1b6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4a6dcf108030a1679601e7c7a39a0f09b13d81a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65259014"
---
# <a name="single-sign-on-event-10727"></a><span data-ttu-id="1f68a-102">シングル サインオン:イベント 10727</span><span class="sxs-lookup"><span data-stu-id="1f68a-102">Single Sign-On: Event 10727</span></span>
## <a name="details"></a><span data-ttu-id="1f68a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1f68a-103">Details</span></span>  

|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="1f68a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1f68a-104">Product Name</span></span>   |                                                        <span data-ttu-id="1f68a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1f68a-105">Enterprise Single Sign-On</span></span>                                                         |
| <span data-ttu-id="1f68a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1f68a-106">Product Version</span></span> |                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    <span data-ttu-id="1f68a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1f68a-107">Event ID</span></span>     |                                                                  <span data-ttu-id="1f68a-108">10727</span><span class="sxs-lookup"><span data-stu-id="1f68a-108">10727</span></span>                                                                   |
|  <span data-ttu-id="1f68a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1f68a-109">Event Source</span></span>   |                                                                  <span data-ttu-id="1f68a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1f68a-110">ENTSSO</span></span>                                                                  |
|    <span data-ttu-id="1f68a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1f68a-111">Component</span></span>    |                                                                   <span data-ttu-id="1f68a-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="1f68a-112">N\A</span></span>                                                                    |
|  <span data-ttu-id="1f68a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1f68a-113">Symbolic Name</span></span>  |                                                      <span data-ttu-id="1f68a-114">SSO_WARN_REPLAY_RECORD_FAILED</span><span class="sxs-lookup"><span data-stu-id="1f68a-114">SSO_WARN_REPLAY_RECORD_FAILED</span></span>                                                       |
|  <span data-ttu-id="1f68a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1f68a-115">Message Text</span></span>   | <span data-ttu-id="1f68a-116">再生の保存された外部パスワード変更 failed.%r</span><span class="sxs-lookup"><span data-stu-id="1f68a-116">Replay of the stored external password change failed.%r</span></span><br /><br /> <span data-ttu-id="1f68a-117">アダプター: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="1f68a-117">Adapter: %1%r</span></span><br /><br /> <span data-ttu-id="1f68a-118">ファイル名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="1f68a-118">File Name: %2%r</span></span><br /><br /> <span data-ttu-id="1f68a-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="1f68a-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="1f68a-120">説明</span><span class="sxs-lookup"><span data-stu-id="1f68a-120">Explanation</span></span>  
 <span data-ttu-id="1f68a-121">この警告は、SSO が再生ファイルに記録されたパスワードの変更を再生することを示します。</span><span class="sxs-lookup"><span data-stu-id="1f68a-121">This Warning indicates that SSO was unable to replay a password change recorded in the replay file.</span></span>  

 <span data-ttu-id="1f68a-122">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f68a-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="1f68a-123">進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。</span><span class="sxs-lookup"><span data-stu-id="1f68a-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="1f68a-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1f68a-124">User Action</span></span>  
 <span data-ttu-id="1f68a-125">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1f68a-125">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="1f68a-126">システムおよびアプリケーションのイベント ログで関連するイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f68a-126">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="1f68a-127">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f68a-127">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="1f68a-128">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="1f68a-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="1f68a-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="1f68a-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
