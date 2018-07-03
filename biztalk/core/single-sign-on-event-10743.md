---
title: 'シングル サインオン: イベント 10743 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2908bc9-1fac-4ab9-869f-0c5512864da4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd0c8c170a17fade96daa0b9ecc0a3613afb1236
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003667"
---
# <a name="single-sign-on-event-10743"></a><span data-ttu-id="de637-102">シングル サインオン: イベント 10743</span><span class="sxs-lookup"><span data-stu-id="de637-102">Single Sign-On: Event 10743</span></span>
## <a name="details"></a><span data-ttu-id="de637-103">詳細</span><span class="sxs-lookup"><span data-stu-id="de637-103">Details</span></span>  

|                 |                                                                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="de637-104">製品名</span><span class="sxs-lookup"><span data-stu-id="de637-104">Product Name</span></span>   |                                                                   <span data-ttu-id="de637-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="de637-105">Enterprise Single Sign-On</span></span>                                                                    |
| <span data-ttu-id="de637-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="de637-106">Product Version</span></span> |                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                   |
|    <span data-ttu-id="de637-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="de637-107">Event ID</span></span>     |                                                                             <span data-ttu-id="de637-108">10743</span><span class="sxs-lookup"><span data-stu-id="de637-108">10743</span></span>                                                                              |
|  <span data-ttu-id="de637-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="de637-109">Event Source</span></span>   |                                                                             <span data-ttu-id="de637-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="de637-110">ENTSSO</span></span>                                                                             |
|    <span data-ttu-id="de637-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="de637-111">Component</span></span>    |                                                                              <span data-ttu-id="de637-112">N\A</span><span class="sxs-lookup"><span data-stu-id="de637-112">N\A</span></span>                                                                               |
|  <span data-ttu-id="de637-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="de637-113">Symbolic Name</span></span>  |                                                                    <span data-ttu-id="de637-114">SSO_ERROR_REPLAY_STOPPED</span><span class="sxs-lookup"><span data-stu-id="de637-114">SSO_ERROR_REPLAY_STOPPED</span></span>                                                                    |
|  <span data-ttu-id="de637-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="de637-115">Message Text</span></span>   | <span data-ttu-id="de637-116">保存された外部パスワード変更の再生はエラーのため停止しました。%r</span><span class="sxs-lookup"><span data-stu-id="de637-116">Replay of stored external password changes stopped due to errors.%r</span></span><br /><br /> <span data-ttu-id="de637-117">再生ファイル: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="de637-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="de637-118">追加データ: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="de637-118">Additional Data: %2%r</span></span><br /><br /> <span data-ttu-id="de637-119">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="de637-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="de637-120">説明</span><span class="sxs-lookup"><span data-stu-id="de637-120">Explanation</span></span>  
 <span data-ttu-id="de637-121">このエラー イベントは、保存された外部パスワード変更の再生がエラーのために停止したことを示します。</span><span class="sxs-lookup"><span data-stu-id="de637-121">This Error event indicates that replay of stored external password changes stopped due to errors.</span></span>  

 <span data-ttu-id="de637-122">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="de637-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="de637-123">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="de637-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="de637-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="de637-124">User Action</span></span>  
 <span data-ttu-id="de637-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="de637-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="de637-126">関連するイベントについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="de637-126">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="de637-127">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de637-127">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="de637-128">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="de637-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="de637-129">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="de637-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
