---
title: シングル サインオン:イベント 10507 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b02d8dfa-7655-471e-84af-e58d08c3cefd
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c147e2cbd5beb0e6c07519b35b700aa59b2b00dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398877"
---
# <a name="single-sign-on-event-10507"></a><span data-ttu-id="9ca35-102">シングル サインオン:イベント 10507</span><span class="sxs-lookup"><span data-stu-id="9ca35-102">Single Sign-On: Event 10507</span></span>
## <a name="details"></a><span data-ttu-id="9ca35-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9ca35-103">Details</span></span>  

|                 |                                                                 |
|-----------------|-----------------------------------------------------------------|
|  <span data-ttu-id="9ca35-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9ca35-104">Product Name</span></span>   |                    <span data-ttu-id="9ca35-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="9ca35-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="9ca35-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9ca35-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]    |
|    <span data-ttu-id="9ca35-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9ca35-107">Event ID</span></span>     |                              <span data-ttu-id="9ca35-108">10504</span><span class="sxs-lookup"><span data-stu-id="9ca35-108">10504</span></span>                              |
|  <span data-ttu-id="9ca35-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9ca35-109">Event Source</span></span>   |                             <span data-ttu-id="9ca35-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9ca35-110">ENTSSO</span></span>                              |
|    <span data-ttu-id="9ca35-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9ca35-111">Component</span></span>    |                               <span data-ttu-id="9ca35-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="9ca35-112">N\A</span></span>                               |
|  <span data-ttu-id="9ca35-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9ca35-113">Symbolic Name</span></span>  |                 <span data-ttu-id="9ca35-114">SSO_INFO_SERVICE_INSTALL_FAILED</span><span class="sxs-lookup"><span data-stu-id="9ca35-114">SSO_INFO_SERVICE_INSTALL_FAILED</span></span>                 |
|  <span data-ttu-id="9ca35-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9ca35-115">Message Text</span></span>   | <span data-ttu-id="9ca35-116">SSO service.%r のインストールに失敗しました</span><span class="sxs-lookup"><span data-stu-id="9ca35-116">Failed to install the SSO service.%r</span></span><br /><br /> <span data-ttu-id="9ca35-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="9ca35-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="9ca35-118">説明</span><span class="sxs-lookup"><span data-stu-id="9ca35-118">Explanation</span></span>  
 <span data-ttu-id="9ca35-119">このイベントは、ENTSSO サービスがインストールに失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="9ca35-119">This event indicates that the ENTSSO Service failed to install.</span></span> <span data-ttu-id="9ca35-120">このイベントは、エンタープライズ シングル サインオンの手動インストール時にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="9ca35-120">This event can only occur during a manual installation of Enterprise Single Sign-On.</span></span>  

## <a name="user-action"></a><span data-ttu-id="9ca35-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9ca35-121">User Action</span></span>  
 <span data-ttu-id="9ca35-122">このイベントを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9ca35-122">To resolve this event, do the following:</span></span>  

- <span data-ttu-id="9ca35-123">ENTSSO または他のサービスから関連するエラーのアプリケーションとシステムの両方のイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="9ca35-123">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  

  <span data-ttu-id="9ca35-124">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="9ca35-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="9ca35-125">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="9ca35-125">Installing SSO</span></span>](../core/installing-sso.md)  

- [<span data-ttu-id="9ca35-126">Enterprise Single Sign-On の実装</span><span class="sxs-lookup"><span data-stu-id="9ca35-126">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
