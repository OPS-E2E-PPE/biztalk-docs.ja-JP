---
title: 'シングル サインオン: イベント 10510 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4553ad4c-9553-4b8b-b3a3-72aed2a61202
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6043dabf397bb987b58707885cbf91d36de50eab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011347"
---
# <a name="single-sign-on-event-10510"></a><span data-ttu-id="e1238-102">シングル サインオン: イベント 10510</span><span class="sxs-lookup"><span data-stu-id="e1238-102">Single Sign-On: Event 10510</span></span>
## <a name="details"></a><span data-ttu-id="e1238-103">詳細</span><span class="sxs-lookup"><span data-stu-id="e1238-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="e1238-104">製品名</span><span class="sxs-lookup"><span data-stu-id="e1238-104">Product Name</span></span>   |                 <span data-ttu-id="e1238-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="e1238-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="e1238-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="e1238-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="e1238-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="e1238-107">Event ID</span></span>     |                           <span data-ttu-id="e1238-108">10510</span><span class="sxs-lookup"><span data-stu-id="e1238-108">10510</span></span>                            |
|  <span data-ttu-id="e1238-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="e1238-109">Event Source</span></span>   |                           <span data-ttu-id="e1238-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="e1238-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="e1238-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="e1238-111">Component</span></span>    |                            <span data-ttu-id="e1238-112">N\A</span><span class="sxs-lookup"><span data-stu-id="e1238-112">N\A</span></span>                             |
|  <span data-ttu-id="e1238-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="e1238-113">Symbolic Name</span></span>  |                  <span data-ttu-id="e1238-114">SSO_INFO_DLL_LOAD_FAILED</span><span class="sxs-lookup"><span data-stu-id="e1238-114">SSO_INFO_DLL_LOAD_FAILED</span></span>                  |
|  <span data-ttu-id="e1238-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="e1238-115">Message Text</span></span>   |   <span data-ttu-id="e1238-116">%1 を読み込めませんでした。</span><span class="sxs-lookup"><span data-stu-id="e1238-116">Failed to load %1.</span></span> <span data-ttu-id="e1238-117">このファイルは使用可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1238-117">Check that this file is available.</span></span>    |

## <a name="explanation"></a><span data-ttu-id="e1238-118">説明</span><span class="sxs-lookup"><span data-stu-id="e1238-118">Explanation</span></span>  
 <span data-ttu-id="e1238-119">この情報イベントは、SSO サービスが DLL を読み込めなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="e1238-119">This Information event indicates that the SSO service has failed to load the DLL.</span></span>  

## <a name="user-action"></a><span data-ttu-id="e1238-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="e1238-120">User Action</span></span>  
 <span data-ttu-id="e1238-121">このイベントを解決するには、次のいずれかの操作 (あるいは複数の操作) を行います。</span><span class="sxs-lookup"><span data-stu-id="e1238-121">To resolve this event, do one or more of the following:</span></span>  

- <span data-ttu-id="e1238-122">DLL が SSO インストール ディレクトリ (通常、C:\Program Files\Common Files\Enterprise Single Sign-On) にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e1238-122">Verify the DLL is located in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On.</span></span> <span data-ttu-id="e1238-123">SSO インストール ディレクトリが違う可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1238-123">Your SSO installation directory may be different.</span></span>  

- <span data-ttu-id="e1238-124">1 つの DLL が不足または破損している場合は、DLL の置き換えを試みてからサービスを再起動してください。</span><span class="sxs-lookup"><span data-stu-id="e1238-124">If the single DLL is missing or corrupted, attempt to replace it and then restart the service.</span></span>  

  <span data-ttu-id="e1238-125">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="e1238-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="e1238-126">Enterprise Single Sign-On の実装</span><span class="sxs-lookup"><span data-stu-id="e1238-126">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
