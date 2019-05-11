---
title: シングル サインオン:イベント 10652 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae7fe452-bcec-4722-8ec6-78d4fe462a0a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df470103391e41cdac109e5b58af0514d402f04a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397658"
---
# <a name="single-sign-on-event-10652"></a><span data-ttu-id="67e36-102">シングル サインオン:イベント 10652</span><span class="sxs-lookup"><span data-stu-id="67e36-102">Single Sign-On: Event 10652</span></span>
## <a name="details"></a><span data-ttu-id="67e36-103">詳細</span><span class="sxs-lookup"><span data-stu-id="67e36-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="67e36-104">製品名</span><span class="sxs-lookup"><span data-stu-id="67e36-104">Product Name</span></span>   |                         <span data-ttu-id="67e36-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="67e36-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="67e36-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="67e36-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="67e36-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="67e36-107">Event ID</span></span>     |                                   <span data-ttu-id="67e36-108">10652</span><span class="sxs-lookup"><span data-stu-id="67e36-108">10652</span></span>                                   |
|  <span data-ttu-id="67e36-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="67e36-109">Event Source</span></span>   |                                  <span data-ttu-id="67e36-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="67e36-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="67e36-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="67e36-111">Component</span></span>    |                                    <span data-ttu-id="67e36-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="67e36-112">N\A</span></span>                                    |
|  <span data-ttu-id="67e36-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="67e36-113">Symbolic Name</span></span>  |                   <span data-ttu-id="67e36-114">SSO_ERROR_PASSWORD_SYNC_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="67e36-114">SSO_ERROR_PASSWORD_SYNC_START_FAILED</span></span>                    |
|  <span data-ttu-id="67e36-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="67e36-115">Message Text</span></span>   | <span data-ttu-id="67e36-116">Initialize.%r にパスワード同期サービスが失敗しました</span><span class="sxs-lookup"><span data-stu-id="67e36-116">Password sync services failed to initialize.%r</span></span><br /><br /> <span data-ttu-id="67e36-117">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="67e36-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="67e36-118">説明</span><span class="sxs-lookup"><span data-stu-id="67e36-118">Explanation</span></span>  
 <span data-ttu-id="67e36-119">このエラー イベントは、例外が原因で、パスワード同期サービスを開始できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="67e36-119">This Error event indicates that the Password Sync Service could not start due to an exception.</span></span>  

## <a name="user-action"></a><span data-ttu-id="67e36-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="67e36-120">User Action</span></span>  
 <span data-ttu-id="67e36-121">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="67e36-121">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="67e36-122">ENTSSO または他のサービスから関連するエラーのアプリケーションとシステムの両方のイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="67e36-122">Check both the Application and System event logs for related errors from ENTSSO or other services.</span></span>  

  <span data-ttu-id="67e36-123">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="67e36-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="67e36-124">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="67e36-124">Password Synchronization</span></span>](../core/password-synchronization2.md)
