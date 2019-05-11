---
title: シングル サインオン:イベント 10503 |Microsoft Docs
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
ms.openlocfilehash: 72b82421d4c70833f085b8e95c75c60cb1944545
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243447"
---
# <a name="single-sign-on-event-10503"></a><span data-ttu-id="574e9-102">シングル サインオン:イベント 10503</span><span class="sxs-lookup"><span data-stu-id="574e9-102">Single Sign-On: Event 10503</span></span>
## <a name="details"></a><span data-ttu-id="574e9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="574e9-103">Details</span></span>  

|                 |                                                               |
|-----------------|---------------------------------------------------------------|
|  <span data-ttu-id="574e9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="574e9-104">Product Name</span></span>   |                   <span data-ttu-id="574e9-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="574e9-105">Enterprise Single Sign-On</span></span>                   |
| <span data-ttu-id="574e9-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="574e9-106">Product Version</span></span> |  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="574e9-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="574e9-107">Event ID</span></span>     |                             <span data-ttu-id="574e9-108">10503</span><span class="sxs-lookup"><span data-stu-id="574e9-108">10503</span></span>                             |
|  <span data-ttu-id="574e9-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="574e9-109">Event Source</span></span>   |                            <span data-ttu-id="574e9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="574e9-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="574e9-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="574e9-111">Component</span></span>    |                              <span data-ttu-id="574e9-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="574e9-112">N\A</span></span>                              |
|  <span data-ttu-id="574e9-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="574e9-113">Symbolic Name</span></span>  |                <span data-ttu-id="574e9-114">SSO_ERROR_SERVICE_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="574e9-114">SSO_ERROR_SERVICE_START_FAILED</span></span>                 |
|  <span data-ttu-id="574e9-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="574e9-115">Message Text</span></span>   | <span data-ttu-id="574e9-116">Start.%r SSO サービスが失敗しました</span><span class="sxs-lookup"><span data-stu-id="574e9-116">The SSO service failed to start.%r</span></span><br /><br /> <span data-ttu-id="574e9-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="574e9-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="574e9-118">説明</span><span class="sxs-lookup"><span data-stu-id="574e9-118">Explanation</span></span>  
 <span data-ttu-id="574e9-119">このエラー イベントは、例外により、ENTSSO サービスを開始できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="574e9-119">This Error event indicates that the ENTSSO Service could not start due to an exception.</span></span>  

## <a name="user-action"></a><span data-ttu-id="574e9-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="574e9-120">User Action</span></span>  
 <span data-ttu-id="574e9-121">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="574e9-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="574e9-122">ENTSSO または他のサービスから関連するエラーのアプリケーションとシステムの両方のイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="574e9-122">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  

  <span data-ttu-id="574e9-123">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="574e9-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="574e9-124">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="574e9-124">Using SSO</span></span>](../core/using-sso.md)
