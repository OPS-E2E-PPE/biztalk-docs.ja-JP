---
title: 'シングル サインオン: イベント 10748 |Microsoft Docs'
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
ms.openlocfilehash: 2f36c031e7ee84179c82a70cc8bbaaeca95df773
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013891"
---
# <a name="single-sign-on-event-10748"></a><span data-ttu-id="ea733-102">シングル サインオン: イベント 10748</span><span class="sxs-lookup"><span data-stu-id="ea733-102">Single Sign-On: Event 10748</span></span>
## <a name="details"></a><span data-ttu-id="ea733-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ea733-103">Details</span></span>  

|                 |                                                                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ea733-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ea733-104">Product Name</span></span>   |                                                                                              <span data-ttu-id="ea733-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="ea733-105">Enterprise Single Sign-On</span></span>                                                                                              |
| <span data-ttu-id="ea733-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ea733-106">Product Version</span></span> |                                                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                              |
|    <span data-ttu-id="ea733-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ea733-107">Event ID</span></span>     |                                                                                                        <span data-ttu-id="ea733-108">10748</span><span class="sxs-lookup"><span data-stu-id="ea733-108">10748</span></span>                                                                                                        |
|  <span data-ttu-id="ea733-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ea733-109">Event Source</span></span>   |                                                                                                       <span data-ttu-id="ea733-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="ea733-110">ENTSSO</span></span>                                                                                                        |
|    <span data-ttu-id="ea733-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ea733-111">Component</span></span>    |                                                                                                         <span data-ttu-id="ea733-112">N\A</span><span class="sxs-lookup"><span data-stu-id="ea733-112">N\A</span></span>                                                                                                         |
|  <span data-ttu-id="ea733-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ea733-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="ea733-114">SSO_WARN_PS_ADAPTER_NOT_RUNNING</span><span class="sxs-lookup"><span data-stu-id="ea733-114">SSO_WARN_PS_ADAPTER_NOT_RUNNING</span></span>                                                                                           |
|  <span data-ttu-id="ea733-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ea733-115">Message Text</span></span>   | <span data-ttu-id="ea733-116">接続先アダプターに接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="ea733-116">Could not contact the destination adapter.</span></span><br /><br /> <span data-ttu-id="ea733-117">実行されていないか、初期化されていない可能性があります。%r</span><span class="sxs-lookup"><span data-stu-id="ea733-117">It may not be running or initialized.%r</span></span><br /><br /> <span data-ttu-id="ea733-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="ea733-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="ea733-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="ea733-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="ea733-120">SSO サーバー名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="ea733-120">SSO Server Name: %3%r</span></span><br /><br /> <span data-ttu-id="ea733-121">エラー コード: %4</span><span class="sxs-lookup"><span data-stu-id="ea733-121">Error Code: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="ea733-122">説明</span><span class="sxs-lookup"><span data-stu-id="ea733-122">Explanation</span></span>  
 <span data-ttu-id="ea733-123">この警告イベントは、パスワード同期で、指定されたパスワード同期アダプターに接続できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="ea733-123">This Warning event indicates that Password Synchronization could not contact the specified password sync adapter.</span></span>  

## <a name="user-action"></a><span data-ttu-id="ea733-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ea733-124">User Action</span></span>  
 <span data-ttu-id="ea733-125">この警告を解消するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="ea733-125">To resolve this warning, do one or more of the following:</span></span>  

- <span data-ttu-id="ea733-126">外部アダプターを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea733-126">Check the external adapter.</span></span>  

- <span data-ttu-id="ea733-127">MMC スナップインまたはコマンド ライン ツールを使用してアダプターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ea733-127">Use the MMC Snap-In or command line tools to enable the adapter.</span></span>  

- <span data-ttu-id="ea733-128">関連するエラーについては、システムおよびアプリケーションのイベント ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea733-128">Check the system and application event logs for associated errors.</span></span>  

  <span data-ttu-id="ea733-129">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea733-129">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="ea733-130">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="ea733-130">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
