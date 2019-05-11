---
title: シングル サインオン:イベント 10707 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59629786-4f98-4861-aba3-153670bafc12
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e323f9b712e566278bf43224611b2d39e74dcecb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397281"
---
# <a name="single-sign-on-event-10707"></a><span data-ttu-id="224ad-102">シングル サインオン:イベント 10707</span><span class="sxs-lookup"><span data-stu-id="224ad-102">Single Sign-On: Event 10707</span></span>
## <a name="details"></a><span data-ttu-id="224ad-103">詳細</span><span class="sxs-lookup"><span data-stu-id="224ad-103">Details</span></span>  

|                 |                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="224ad-104">製品名</span><span class="sxs-lookup"><span data-stu-id="224ad-104">Product Name</span></span>   |                                                                       <span data-ttu-id="224ad-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="224ad-105">Enterprise Single Sign-On</span></span>                                                                        |
| <span data-ttu-id="224ad-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="224ad-106">Product Version</span></span> |                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    <span data-ttu-id="224ad-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="224ad-107">Event ID</span></span>     |                                                                                 <span data-ttu-id="224ad-108">10707</span><span class="sxs-lookup"><span data-stu-id="224ad-108">10707</span></span>                                                                                  |
|  <span data-ttu-id="224ad-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="224ad-109">Event Source</span></span>   |                                                                                 <span data-ttu-id="224ad-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="224ad-110">ENTSSO</span></span>                                                                                 |
|    <span data-ttu-id="224ad-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="224ad-111">Component</span></span>    |                                                                                  <span data-ttu-id="224ad-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="224ad-112">N\A</span></span>                                                                                   |
|  <span data-ttu-id="224ad-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="224ad-113">Symbolic Name</span></span>  |                                                                        <span data-ttu-id="224ad-114">SSO_WARN_PS_NO_APP_SYNC</span><span class="sxs-lookup"><span data-stu-id="224ad-114">SSO_WARN_PS_NO_APP_SYNC</span></span>                                                                         |
|  <span data-ttu-id="224ad-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="224ad-115">Message Text</span></span>   | <span data-ttu-id="224ad-116">このアダプターのパスワード同期フラグは、パスワード同期を許可する必要があり、グローバル フラグに一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="224ad-116">Password sync flags for this adapter must allow password sync and must match the global flags.</span></span> <span data-ttu-id="224ad-117">アダプタ フラグおよびグローバル flags.%r を確認してください。</span><span class="sxs-lookup"><span data-stu-id="224ad-117">Check the adapter flags and the global flags.%r</span></span><br /><br /> <span data-ttu-id="224ad-118">アダプタ: %1</span><span class="sxs-lookup"><span data-stu-id="224ad-118">Adapter: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="224ad-119">説明</span><span class="sxs-lookup"><span data-stu-id="224ad-119">Explanation</span></span>  
 <span data-ttu-id="224ad-120">この警告イベントは、このアダプターのパスワード同期フラグがパスワード同期を許可する必要がありますする必要がありますには、グローバル フラグと一致することを示します。</span><span class="sxs-lookup"><span data-stu-id="224ad-120">This Warning event indicates that password sync flags for this adapter must allow password sync and must match the global flags.</span></span>  

 <span data-ttu-id="224ad-121">パスワード同期アダプターのパスワード同期は、2 つのフラグによって制御されますが、1 つの送信を許可 (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL) の外部システムにパスワードと別の外部システム (SSO_FLAG_PARTIAL_ からパスワードの受信を許可します。SYNC_FROM_EXTERNAL_TO_DB)。</span><span class="sxs-lookup"><span data-stu-id="224ad-121">Password sync for a password sync adapter is controlled by two flags, one allows sending of password to external systems (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL) and another which allows receiving of passwords from external systems (SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB).</span></span> <span data-ttu-id="224ad-122">正常にパスワード同期これら両方の「グローバル フラグ」と特定のアダプター フラグも設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="224ad-122">For successfull password sync these must be set for both the “global flags” and also for the specific adapter flags.</span></span> <span data-ttu-id="224ad-123">この警告イベントは、外部パスワード同期アダプターによってパスワード同期が要求され、「グローバル フラグ」とアダプター フラグの両方のこれらのフラグも設定されているときに発行されます。</span><span class="sxs-lookup"><span data-stu-id="224ad-123">This warning event is issued when password sync is requested by an external password sync adapter and neither of these flags is set for both the “global flags” and the adapter flags.</span></span>  

## <a name="user-action"></a><span data-ttu-id="224ad-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="224ad-124">User Action</span></span>  
 <span data-ttu-id="224ad-125">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="224ad-125">To resolve this warning, do the following:</span></span>  

-   <span data-ttu-id="224ad-126">SSO 管理 MMC スナップインを使用して (システム &#124; 文字です。プロパティと &#124; 文字です。オプション) またはコマンド ライン ツール  `ssomanage –enable winsync/extsync` グローバル フラグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="224ad-126">Use the SSO Admin MMC Snap-In (System &#124; Properties &#124; Options) or command line tool  `ssomanage –enable winsync/extsync` to enable the global flags.</span></span>  

## <a name="more-info"></a><span data-ttu-id="224ad-127">詳細情報</span><span class="sxs-lookup"><span data-stu-id="224ad-127">More info</span></span>

- <span data-ttu-id="224ad-128">**エンタープライズ シングル サインオン フラグ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="224ad-128">**Enterprise Single Sign-On Flags** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  

- [<span data-ttu-id="224ad-129">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="224ad-129">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
