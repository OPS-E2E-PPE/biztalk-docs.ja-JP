---
title: "シングル サインオン: イベント 10507 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b02d8dfa-7655-471e-84af-e58d08c3cefd
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9f184acaddf64a68b38211c84c86f418af42adf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10507"></a><span data-ttu-id="bfa0b-102">シングル サインオン: イベント 10507</span><span class="sxs-lookup"><span data-stu-id="bfa0b-102">Single Sign-On: Event 10507</span></span>
## <a name="details"></a><span data-ttu-id="bfa0b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bfa0b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bfa0b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bfa0b-104">Product Name</span></span>|<span data-ttu-id="bfa0b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="bfa0b-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="bfa0b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bfa0b-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="bfa0b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bfa0b-107">Event ID</span></span>|<span data-ttu-id="bfa0b-108">10504</span><span class="sxs-lookup"><span data-stu-id="bfa0b-108">10504</span></span>|  
|<span data-ttu-id="bfa0b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bfa0b-109">Event Source</span></span>|<span data-ttu-id="bfa0b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bfa0b-110">ENTSSO</span></span>|  
|<span data-ttu-id="bfa0b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bfa0b-111">Component</span></span>|<span data-ttu-id="bfa0b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="bfa0b-112">N\A</span></span>|  
|<span data-ttu-id="bfa0b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bfa0b-113">Symbolic Name</span></span>|<span data-ttu-id="bfa0b-114">SSO_INFO_SERVICE_INSTALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="bfa0b-114">SSO_INFO_SERVICE_INSTALL_FAILED</span></span>|  
|<span data-ttu-id="bfa0b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bfa0b-115">Message Text</span></span>|<span data-ttu-id="bfa0b-116">SSO サービスをインストールできませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="bfa0b-116">Failed to install the SSO service.%r</span></span><br /><br /> <span data-ttu-id="bfa0b-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="bfa0b-117">Error Code: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="bfa0b-118">説明</span><span class="sxs-lookup"><span data-stu-id="bfa0b-118">Explanation</span></span>  
 <span data-ttu-id="bfa0b-119">このイベントは、ENTSSO サービスをインストールできなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="bfa0b-119">This event indicates that the ENTSSO Service failed to install.</span></span> <span data-ttu-id="bfa0b-120">このイベントは、エンタープライズ シングル サインオンの手動でのインストール中にのみ発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bfa0b-120">This event can only occur during a manual installation of Enterprise Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bfa0b-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bfa0b-121">User Action</span></span>  
 <span data-ttu-id="bfa0b-122">このイベントを解決するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bfa0b-122">To resolve this event, do the following:</span></span>  
  
-   <span data-ttu-id="bfa0b-123">ENTSSO または他のサービスからの関連するエラーについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="bfa0b-123">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  
  
 <span data-ttu-id="bfa0b-124">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="bfa0b-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="bfa0b-125">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="bfa0b-125">Installing SSO</span></span>](../core/installing-sso.md)  
  
-   [<span data-ttu-id="bfa0b-126">エンタープライズ シングル サインオンを実装します。</span><span class="sxs-lookup"><span data-stu-id="bfa0b-126">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)