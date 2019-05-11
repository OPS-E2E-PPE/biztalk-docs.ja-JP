---
title: シングル サインオン:イベント 10748 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b4b18ea-6565-4c0b-89f8-30a8c67601ba
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 518f12cbf89b345775c6e486d522ca1e667d9142
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395484"
---
# <a name="single-sign-on-event-10748"></a><span data-ttu-id="ecc39-102">シングル サインオン:イベント 10748</span><span class="sxs-lookup"><span data-stu-id="ecc39-102">Single Sign-On: Event 10748</span></span>
## <a name="details"></a><span data-ttu-id="ecc39-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ecc39-103">Details</span></span>  

|                 |                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ecc39-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ecc39-104">Product Name</span></span>   |                                                                                              <span data-ttu-id="ecc39-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ecc39-105">Enterprise Single Sign-On</span></span>                                                                                              |
| <span data-ttu-id="ecc39-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ecc39-106">Product Version</span></span> |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    <span data-ttu-id="ecc39-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ecc39-107">Event ID</span></span>     |                                                                                                        <span data-ttu-id="ecc39-108">10748</span><span class="sxs-lookup"><span data-stu-id="ecc39-108">10748</span></span>                                                                                                        |
|  <span data-ttu-id="ecc39-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ecc39-109">Event Source</span></span>   |                                                                                                       <span data-ttu-id="ecc39-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ecc39-110">ENTSSO</span></span>                                                                                                        |
|    <span data-ttu-id="ecc39-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ecc39-111">Component</span></span>    |                                                                                                         <span data-ttu-id="ecc39-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="ecc39-112">N\A</span></span>                                                                                                         |
|  <span data-ttu-id="ecc39-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ecc39-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="ecc39-114">SSO_WARN_PS_ADAPTER_NOT_RUNNING</span><span class="sxs-lookup"><span data-stu-id="ecc39-114">SSO_WARN_PS_ADAPTER_NOT_RUNNING</span></span>                                                                                           |
|  <span data-ttu-id="ecc39-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ecc39-115">Message Text</span></span>   | <span data-ttu-id="ecc39-116">変換先アダプターに接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="ecc39-116">Could not contact the destination adapter.</span></span><br /><br /> <span data-ttu-id="ecc39-117">実行中または initialized.%r はなりません。</span><span class="sxs-lookup"><span data-stu-id="ecc39-117">It may not be running or initialized.%r</span></span><br /><br /> <span data-ttu-id="ecc39-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ecc39-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="ecc39-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="ecc39-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="ecc39-120">SSO サーバー名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="ecc39-120">SSO Server Name: %3%r</span></span><br /><br /> <span data-ttu-id="ecc39-121">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="ecc39-121">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="ecc39-122">説明</span><span class="sxs-lookup"><span data-stu-id="ecc39-122">Explanation</span></span>  
 <span data-ttu-id="ecc39-123">この警告イベントは、パスワード同期が、指定したパスワード同期アダプターに接続できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ecc39-123">This Warning event indicates that Password Synchronization could not contact the specified password sync adapter.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ecc39-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ecc39-124">User Action</span></span>  
 <span data-ttu-id="ecc39-125">この警告を解決するには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ecc39-125">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="ecc39-126">外部アダプターを確認します。</span><span class="sxs-lookup"><span data-stu-id="ecc39-126">Check the external adapter.</span></span>  

- <span data-ttu-id="ecc39-127">アダプターを有効にするのにには、MMC スナップインまたはコマンド ライン ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="ecc39-127">Use the MMC Snap-In or command line tools to enable the adapter.</span></span>  

- <span data-ttu-id="ecc39-128">関連付けられているエラーのシステムおよびアプリケーション イベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="ecc39-128">Check the system and application event logs for associated errors.</span></span>  

  <span data-ttu-id="ecc39-129">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecc39-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="ecc39-130">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="ecc39-130">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
