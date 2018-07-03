---
title: 'シングル サインオン: イベント 10515 |Microsoft Docs'
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
ms.openlocfilehash: f1c3d7498bcd6a045936103d682d3643761a182c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980819"
---
# <a name="single-sign-on-event-10515"></a><span data-ttu-id="23eaf-102">シングル サインオン: イベント 10515</span><span class="sxs-lookup"><span data-stu-id="23eaf-102">Single Sign-On: Event 10515</span></span>
## <a name="details"></a><span data-ttu-id="23eaf-103">詳細</span><span class="sxs-lookup"><span data-stu-id="23eaf-103">Details</span></span>  
  
|                 |                                                                               |
|-----------------|-------------------------------------------------------------------------------|
|  <span data-ttu-id="23eaf-104">製品名</span><span class="sxs-lookup"><span data-stu-id="23eaf-104">Product Name</span></span>   |                           <span data-ttu-id="23eaf-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="23eaf-105">Enterprise Single Sign-On</span></span>                           |
| <span data-ttu-id="23eaf-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="23eaf-106">Product Version</span></span> |          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]           |
|    <span data-ttu-id="23eaf-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="23eaf-107">Event ID</span></span>     |                                     <span data-ttu-id="23eaf-108">10515</span><span class="sxs-lookup"><span data-stu-id="23eaf-108">10515</span></span>                                     |
|  <span data-ttu-id="23eaf-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="23eaf-109">Event Source</span></span>   |                                    <span data-ttu-id="23eaf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="23eaf-110">ENTSSO</span></span>                                     |
|    <span data-ttu-id="23eaf-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="23eaf-111">Component</span></span>    |                                      <span data-ttu-id="23eaf-112">N\A</span><span class="sxs-lookup"><span data-stu-id="23eaf-112">N\A</span></span>                                      |
|  <span data-ttu-id="23eaf-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="23eaf-113">Symbolic Name</span></span>  |                            <span data-ttu-id="23eaf-114">SSO_ERROR_POLL_DATABASE</span><span class="sxs-lookup"><span data-stu-id="23eaf-114">SSO_ERROR_POLL_DATABASE</span></span>                            |
|  <span data-ttu-id="23eaf-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="23eaf-115">Message Text</span></span>   | <span data-ttu-id="23eaf-116">SSO データベースとの接続が切断されました。</span><span class="sxs-lookup"><span data-stu-id="23eaf-116">Lost contact with the SSO database.</span></span> <span data-ttu-id="23eaf-117">SSO データベースが使用可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="23eaf-117">Check that the SSO database is available.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="23eaf-118">説明</span><span class="sxs-lookup"><span data-stu-id="23eaf-118">Explanation</span></span>  
 <span data-ttu-id="23eaf-119">このエラー イベントは、SSO サービスと SSO データベースとの接続が切断されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="23eaf-119">This Error event indicates that the SSO Service has lost contact with the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="23eaf-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="23eaf-120">User Action</span></span>  
 <span data-ttu-id="23eaf-121">このエラーを解決するには、以下の 1 つ以上の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="23eaf-121">To resolve this error, do one or more of the following:</span></span>  
  
- <span data-ttu-id="23eaf-122">SQL Server (MSSQLSERVER) サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="23eaf-122">Verify that the SQL Server (MSSQLSERVER) service is running.</span></span>  
  
- <span data-ttu-id="23eaf-123">SQL Server がリモート サーバー上で実行されている場合は、ネットワーク接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="23eaf-123">Verify network connectivity to SQL Server if on a remote server.</span></span>  
  
  <span data-ttu-id="23eaf-124">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="23eaf-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
- [<span data-ttu-id="23eaf-125">Enterprise Single Sign-On の実装</span><span class="sxs-lookup"><span data-stu-id="23eaf-125">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)  
  
- [<span data-ttu-id="23eaf-126">SSO データベース情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="23eaf-126">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)  
  
- [<span data-ttu-id="23eaf-127">SSO の構成</span><span class="sxs-lookup"><span data-stu-id="23eaf-127">Configuring SSO</span></span>](../core/configuring-sso.md)  
  
  <span data-ttu-id="23eaf-128">SQL Server オンライン ブックも参照してください。</span><span class="sxs-lookup"><span data-stu-id="23eaf-128">See also SQL Server Books Online</span></span>