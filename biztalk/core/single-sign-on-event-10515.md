---
title: シングル サインオン:イベント 10515 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41edc008-b6d3-401d-97af-80b36ab0ba55
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3071aa76f6a1366c3a17c38a51f81da7048331b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243446"
---
# <a name="single-sign-on-event-10515"></a><span data-ttu-id="94669-102">シングル サインオン:イベント 10515</span><span class="sxs-lookup"><span data-stu-id="94669-102">Single Sign-On: Event 10515</span></span>
## <a name="details"></a><span data-ttu-id="94669-103">詳細</span><span class="sxs-lookup"><span data-stu-id="94669-103">Details</span></span>  
  
|                 |                                                                               |
|-----------------|-------------------------------------------------------------------------------|
|  <span data-ttu-id="94669-104">製品名</span><span class="sxs-lookup"><span data-stu-id="94669-104">Product Name</span></span>   |                           <span data-ttu-id="94669-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="94669-105">Enterprise Single Sign-On</span></span>                           |
| <span data-ttu-id="94669-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="94669-106">Product Version</span></span> |          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]           |
|    <span data-ttu-id="94669-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="94669-107">Event ID</span></span>     |                                     <span data-ttu-id="94669-108">10515</span><span class="sxs-lookup"><span data-stu-id="94669-108">10515</span></span>                                     |
|  <span data-ttu-id="94669-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="94669-109">Event Source</span></span>   |                                    <span data-ttu-id="94669-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="94669-110">ENTSSO</span></span>                                     |
|    <span data-ttu-id="94669-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="94669-111">Component</span></span>    |                                      <span data-ttu-id="94669-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="94669-112">N\A</span></span>                                      |
|  <span data-ttu-id="94669-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="94669-113">Symbolic Name</span></span>  |                            <span data-ttu-id="94669-114">SSO_ERROR_POLL_DATABASE</span><span class="sxs-lookup"><span data-stu-id="94669-114">SSO_ERROR_POLL_DATABASE</span></span>                            |
|  <span data-ttu-id="94669-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="94669-115">Message Text</span></span>   | <span data-ttu-id="94669-116">SSO データベースとの接続が切断されました。</span><span class="sxs-lookup"><span data-stu-id="94669-116">Lost contact with the SSO database.</span></span> <span data-ttu-id="94669-117">SSO データベースが使用可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="94669-117">Check that the SSO database is available.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="94669-118">説明</span><span class="sxs-lookup"><span data-stu-id="94669-118">Explanation</span></span>  
 <span data-ttu-id="94669-119">このエラー イベントは、SSO サービスが SSO データベースとの接続を失ったことを示します。</span><span class="sxs-lookup"><span data-stu-id="94669-119">This Error event indicates that the SSO Service has lost contact with the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="94669-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="94669-120">User Action</span></span>  
 <span data-ttu-id="94669-121">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="94669-121">To resolve this error, do one or more of the following:</span></span>  
  
- <span data-ttu-id="94669-122">SQL Server (MSSQLSERVER) サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="94669-122">Verify that the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
- <span data-ttu-id="94669-123">リモート サーバー上にある場合は、SQL Server へのネットワーク接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="94669-123">Verify network connectivity to SQL Server if on a remote server.</span></span>  
  
  <span data-ttu-id="94669-124">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="94669-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
- [<span data-ttu-id="94669-125">Enterprise Single Sign-On の実装</span><span class="sxs-lookup"><span data-stu-id="94669-125">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  
  
- [<span data-ttu-id="94669-126">SSO データベース情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="94669-126">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
- [<span data-ttu-id="94669-127">SSO の構成</span><span class="sxs-lookup"><span data-stu-id="94669-127">Configuring SSO</span></span>](../core/configuring-sso.md)  
  
  <span data-ttu-id="94669-128">SQL Server オンライン ブックも参照してください。</span><span class="sxs-lookup"><span data-stu-id="94669-128">See also SQL Server Books Online</span></span>