---
title: 'シングル サインオン: イベント 10727 |Microsoft Docs'
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
ms.openlocfilehash: 5f25dd71e223452707ff00e23b6a3a3bc797d10f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970547"
---
# <a name="single-sign-on-event-10727"></a><span data-ttu-id="8065e-102">シングル サインオン: イベント 10727</span><span class="sxs-lookup"><span data-stu-id="8065e-102">Single Sign-On: Event 10727</span></span>
## <a name="details"></a><span data-ttu-id="8065e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8065e-103">Details</span></span>  

|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="8065e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8065e-104">Product Name</span></span>   |                                                        <span data-ttu-id="8065e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="8065e-105">Enterprise Single Sign-On</span></span>                                                         |
| <span data-ttu-id="8065e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8065e-106">Product Version</span></span> |                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    <span data-ttu-id="8065e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8065e-107">Event ID</span></span>     |                                                                  <span data-ttu-id="8065e-108">10727</span><span class="sxs-lookup"><span data-stu-id="8065e-108">10727</span></span>                                                                   |
|  <span data-ttu-id="8065e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8065e-109">Event Source</span></span>   |                                                                  <span data-ttu-id="8065e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="8065e-110">ENTSSO</span></span>                                                                  |
|    <span data-ttu-id="8065e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8065e-111">Component</span></span>    |                                                                   <span data-ttu-id="8065e-112">N\A</span><span class="sxs-lookup"><span data-stu-id="8065e-112">N\A</span></span>                                                                    |
|  <span data-ttu-id="8065e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8065e-113">Symbolic Name</span></span>  |                                                      <span data-ttu-id="8065e-114">SSO_WARN_REPLAY_RECORD_FAILED</span><span class="sxs-lookup"><span data-stu-id="8065e-114">SSO_WARN_REPLAY_RECORD_FAILED</span></span>                                                       |
|  <span data-ttu-id="8065e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8065e-115">Message Text</span></span>   | <span data-ttu-id="8065e-116">保存された外部パスワード変更の再生が失敗しました。%r</span><span class="sxs-lookup"><span data-stu-id="8065e-116">Replay of the stored external password change failed.%r</span></span><br /><br /> <span data-ttu-id="8065e-117">アダプター: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="8065e-117">Adapter: %1%r</span></span><br /><br /> <span data-ttu-id="8065e-118">ファイル名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="8065e-118">File Name: %2%r</span></span><br /><br /> <span data-ttu-id="8065e-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="8065e-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="8065e-120">説明</span><span class="sxs-lookup"><span data-stu-id="8065e-120">Explanation</span></span>  
 <span data-ttu-id="8065e-121">この警告は、再生ファイルに記録されたパスワード変更を SSO が再生できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8065e-121">This Warning indicates that SSO was unable to replay a password change recorded in the replay file.</span></span>  

 <span data-ttu-id="8065e-122">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="8065e-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="8065e-123">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="8065e-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="8065e-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8065e-124">User Action</span></span>  
 <span data-ttu-id="8065e-125">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="8065e-125">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="8065e-126">関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="8065e-126">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="8065e-127">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8065e-127">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="8065e-128">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="8065e-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="8065e-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="8065e-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
