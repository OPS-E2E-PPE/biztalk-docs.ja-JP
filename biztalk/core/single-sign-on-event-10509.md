---
title: シングル サインオン:イベント 10509 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f906823f-db3f-45fc-bf61-cbe6a9566bd7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2911358dd326c5fa7f2673567f53805edb898de0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243419"
---
# <a name="single-sign-on-event-10509"></a><span data-ttu-id="f7d33-102">シングル サインオン:イベント 10509</span><span class="sxs-lookup"><span data-stu-id="f7d33-102">Single Sign-On: Event 10509</span></span>
## <a name="details"></a><span data-ttu-id="f7d33-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f7d33-103">Details</span></span>  

|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  <span data-ttu-id="f7d33-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f7d33-104">Product Name</span></span>   |                   <span data-ttu-id="f7d33-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f7d33-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="f7d33-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f7d33-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="f7d33-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f7d33-107">Event ID</span></span>     |                             <span data-ttu-id="f7d33-108">10509</span><span class="sxs-lookup"><span data-stu-id="f7d33-108">10509</span></span>                              |
|  <span data-ttu-id="f7d33-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f7d33-109">Event Source</span></span>   |                             <span data-ttu-id="f7d33-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f7d33-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="f7d33-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f7d33-111">Component</span></span>    |                              <span data-ttu-id="f7d33-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="f7d33-112">N\A</span></span>                               |
|  <span data-ttu-id="f7d33-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f7d33-113">Symbolic Name</span></span>  |                 <span data-ttu-id="f7d33-114">SSO_INFO_SERVICE_REMOVE_FAILED</span><span class="sxs-lookup"><span data-stu-id="f7d33-114">SSO_INFO_SERVICE_REMOVE_FAILED</span></span>                 |
|  <span data-ttu-id="f7d33-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f7d33-115">Message Text</span></span>   | <span data-ttu-id="f7d33-116">SSO service.%r を削除できませんでした。</span><span class="sxs-lookup"><span data-stu-id="f7d33-116">Failed to remove the SSO service.%r</span></span><br /><br /> <span data-ttu-id="f7d33-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="f7d33-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="f7d33-118">説明</span><span class="sxs-lookup"><span data-stu-id="f7d33-118">Explanation</span></span>  
 <span data-ttu-id="f7d33-119">このイベントは、ENTSSO サービスがアンインストールに失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="f7d33-119">This event indicates that the ENTSSO Service failed to uninstall.</span></span> <span data-ttu-id="f7d33-120">このイベントは、エンタープライズ シングル サインオンの手動アンインストール中にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="f7d33-120">This event can only occur during a manual uninstallation of Enterprise Single Sign-On.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f7d33-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f7d33-121">User Action</span></span>  
 <span data-ttu-id="f7d33-122">このイベントを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f7d33-122">To resolve this event, do the following:</span></span>  

- <span data-ttu-id="f7d33-123">ENTSSO または他のサービスから関連するエラーのアプリケーションとシステムの両方のイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7d33-123">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  

  <span data-ttu-id="f7d33-124">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="f7d33-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="f7d33-125">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="f7d33-125">Installing SSO</span></span>](../core/installing-sso.md)  

- [<span data-ttu-id="f7d33-126">Enterprise Single Sign-On の実装</span><span class="sxs-lookup"><span data-stu-id="f7d33-126">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
