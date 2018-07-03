---
title: 'シングル サインオン: イベント 10503 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04292ae8-8daf-4f5a-837e-fe5dfcd02b10
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b90af01551359b5caa1a5404facc9e3fece95673
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990715"
---
# <a name="single-sign-on-event-10503"></a><span data-ttu-id="34fbf-102">シングル サインオン: イベント 10503</span><span class="sxs-lookup"><span data-stu-id="34fbf-102">Single Sign-On: Event 10503</span></span>
## <a name="details"></a><span data-ttu-id="34fbf-103">詳細</span><span class="sxs-lookup"><span data-stu-id="34fbf-103">Details</span></span>  

|                 |                                                               |
|-----------------|---------------------------------------------------------------|
|  <span data-ttu-id="34fbf-104">製品名</span><span class="sxs-lookup"><span data-stu-id="34fbf-104">Product Name</span></span>   |                   <span data-ttu-id="34fbf-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="34fbf-105">Enterprise Single Sign-On</span></span>                   |
| <span data-ttu-id="34fbf-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="34fbf-106">Product Version</span></span> |  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="34fbf-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="34fbf-107">Event ID</span></span>     |                             <span data-ttu-id="34fbf-108">10503</span><span class="sxs-lookup"><span data-stu-id="34fbf-108">10503</span></span>                             |
|  <span data-ttu-id="34fbf-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="34fbf-109">Event Source</span></span>   |                            <span data-ttu-id="34fbf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="34fbf-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="34fbf-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="34fbf-111">Component</span></span>    |                              <span data-ttu-id="34fbf-112">N\A</span><span class="sxs-lookup"><span data-stu-id="34fbf-112">N\A</span></span>                              |
|  <span data-ttu-id="34fbf-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="34fbf-113">Symbolic Name</span></span>  |                <span data-ttu-id="34fbf-114">SSO_ERROR_SERVICE_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="34fbf-114">SSO_ERROR_SERVICE_START_FAILED</span></span>                 |
|  <span data-ttu-id="34fbf-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="34fbf-115">Message Text</span></span>   | <span data-ttu-id="34fbf-116">SSO サービスを開始できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="34fbf-116">The SSO service failed to start.%r</span></span><br /><br /> <span data-ttu-id="34fbf-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="34fbf-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="34fbf-118">説明</span><span class="sxs-lookup"><span data-stu-id="34fbf-118">Explanation</span></span>  
 <span data-ttu-id="34fbf-119">このエラー イベントは、例外が発生したために ENTSSO サービスを開始できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="34fbf-119">This Error event indicates that the ENTSSO Service could not start due to an exception.</span></span>  

## <a name="user-action"></a><span data-ttu-id="34fbf-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="34fbf-120">User Action</span></span>  
 <span data-ttu-id="34fbf-121">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="34fbf-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="34fbf-122">ENTSSO または他のサービスからの関連するエラーについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="34fbf-122">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  

  <span data-ttu-id="34fbf-123">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="34fbf-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="34fbf-124">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="34fbf-124">Using SSO</span></span>](../core/using-sso.md)
