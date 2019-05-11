---
title: シングル サインオン:イベント 10705 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81456bdd-dfd8-4483-aa76-5ec72350cc70
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e88a77cc05956f50af31094d299b653ce71056f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397289"
---
# <a name="single-sign-on-event-10705"></a><span data-ttu-id="fde05-102">シングル サインオン:イベント 10705</span><span class="sxs-lookup"><span data-stu-id="fde05-102">Single Sign-On: Event 10705</span></span>
## <a name="details"></a><span data-ttu-id="fde05-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fde05-103">Details</span></span>  

|                 |                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="fde05-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fde05-104">Product Name</span></span>   |                                         <span data-ttu-id="fde05-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="fde05-105">Enterprise Single Sign-On</span></span>                                          |
| <span data-ttu-id="fde05-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fde05-106">Product Version</span></span> |                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                         |
|    <span data-ttu-id="fde05-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fde05-107">Event ID</span></span>     |                                                   <span data-ttu-id="fde05-108">10705</span><span class="sxs-lookup"><span data-stu-id="fde05-108">10705</span></span>                                                    |
|  <span data-ttu-id="fde05-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fde05-109">Event Source</span></span>   |                                                   <span data-ttu-id="fde05-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fde05-110">ENTSSO</span></span>                                                   |
|    <span data-ttu-id="fde05-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fde05-111">Component</span></span>    |                                                    <span data-ttu-id="fde05-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="fde05-112">N\A</span></span>                                                     |
|  <span data-ttu-id="fde05-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fde05-113">Symbolic Name</span></span>  |                                          <span data-ttu-id="fde05-114">SSO_WARN_PS_NOT_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="fde05-114">SSO_WARN_PS_NOT_ADAPTER</span></span>                                           |
|  <span data-ttu-id="fde05-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fde05-115">Message Text</span></span>   | <span data-ttu-id="fde05-116">指定されたアダプターはアダプター アプリケーションではありません。</span><span class="sxs-lookup"><span data-stu-id="fde05-116">The specified adapter is not an adapter application.</span></span> <span data-ttu-id="fde05-117">アプリケーション type.%r を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fde05-117">Check the application type.%r</span></span><br /><br /> <span data-ttu-id="fde05-118">アダプタ: %1</span><span class="sxs-lookup"><span data-stu-id="fde05-118">Adapter: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="fde05-119">説明</span><span class="sxs-lookup"><span data-stu-id="fde05-119">Explanation</span></span>  
 <span data-ttu-id="fde05-120">この警告イベントは、指定されたアダプターがアダプター アプリケーションではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="fde05-120">This Warning event indicates that the specified adapter is not an adapter application.</span></span>  

## <a name="user-action"></a><span data-ttu-id="fde05-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fde05-121">User Action</span></span>  
 <span data-ttu-id="fde05-122">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fde05-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="fde05-123">SSO 管理 MMC スナップインを使用して、指定のアダプターを右クリックし、プロパティをアプリケーションの種類を確認したり、コマンド ライン ツール ssops を使用 をクリックして--list および ssops-アプリケーションの種類を決定する表示します。</span><span class="sxs-lookup"><span data-stu-id="fde05-123">Use the SSO Admin MMC Snap-In, right click the specified adapter, and then click Properties to determine the application type or use the command line tool  ssops -list and ssops -display to determine the application type.</span></span>  

- <span data-ttu-id="fde05-124">アダプターのアプリケーションを設定して、SSO 管理 MMC スナップインまたは ssops-addapp を使用します。</span><span class="sxs-lookup"><span data-stu-id="fde05-124">Use the SSO Admin MMC Snap-In or ssops -addapp to set the adapter application.</span></span>  

  <span data-ttu-id="fde05-125">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fde05-125">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="fde05-126">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="fde05-126">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
