---
title: シングル サインオン:イベント 10510 |Microsoft Docs
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
ms.openlocfilehash: 6a3ac20c725492ebd6f7867cdf3c11be3ab7fdab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393933"
---
# <a name="single-sign-on-event-10510"></a><span data-ttu-id="395fd-102">シングル サインオン:イベント 10510</span><span class="sxs-lookup"><span data-stu-id="395fd-102">Single Sign-On: Event 10510</span></span>
## <a name="details"></a><span data-ttu-id="395fd-103">詳細</span><span class="sxs-lookup"><span data-stu-id="395fd-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="395fd-104">製品名</span><span class="sxs-lookup"><span data-stu-id="395fd-104">Product Name</span></span>   |                 <span data-ttu-id="395fd-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="395fd-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="395fd-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="395fd-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="395fd-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="395fd-107">Event ID</span></span>     |                           <span data-ttu-id="395fd-108">10510</span><span class="sxs-lookup"><span data-stu-id="395fd-108">10510</span></span>                            |
|  <span data-ttu-id="395fd-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="395fd-109">Event Source</span></span>   |                           <span data-ttu-id="395fd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="395fd-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="395fd-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="395fd-111">Component</span></span>    |                            <span data-ttu-id="395fd-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="395fd-112">N\A</span></span>                             |
|  <span data-ttu-id="395fd-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="395fd-113">Symbolic Name</span></span>  |                  <span data-ttu-id="395fd-114">SSO_INFO_DLL_LOAD_FAILED</span><span class="sxs-lookup"><span data-stu-id="395fd-114">SSO_INFO_DLL_LOAD_FAILED</span></span>                  |
|  <span data-ttu-id="395fd-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="395fd-115">Message Text</span></span>   |   <span data-ttu-id="395fd-116">%1 を読み込めませんでした。</span><span class="sxs-lookup"><span data-stu-id="395fd-116">Failed to load %1.</span></span> <span data-ttu-id="395fd-117">このファイルは使用可能なことを確認します。</span><span class="sxs-lookup"><span data-stu-id="395fd-117">Check that this file is available.</span></span>    |

## <a name="explanation"></a><span data-ttu-id="395fd-118">説明</span><span class="sxs-lookup"><span data-stu-id="395fd-118">Explanation</span></span>  
 <span data-ttu-id="395fd-119">この情報イベントは、SSO サービスが、DLL の読み込みに失敗したことを示します。</span><span class="sxs-lookup"><span data-stu-id="395fd-119">This Information event indicates that the SSO service has failed to load the DLL.</span></span>  

## <a name="user-action"></a><span data-ttu-id="395fd-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="395fd-120">User Action</span></span>  
 <span data-ttu-id="395fd-121">このイベントを解決するには、次の 1 つ以上の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="395fd-121">To resolve this event, do one or more of the following:</span></span>  

- <span data-ttu-id="395fd-122">DLL が SSO インストール ディレクトリの通常 C:\Program files \common files \enterprise でシングル サインオンであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="395fd-122">Verify the DLL is located in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On.</span></span> <span data-ttu-id="395fd-123">SSO インストール ディレクトリは、異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="395fd-123">Your SSO installation directory may be different.</span></span>  

- <span data-ttu-id="395fd-124">1 つの DLL が見つからないか壊れている場合、しようとして、サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="395fd-124">If the single DLL is missing or corrupted, attempt to replace it and then restart the service.</span></span>  

  <span data-ttu-id="395fd-125">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="395fd-125">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="395fd-126">Enterprise Single Sign-On の実装</span><span class="sxs-lookup"><span data-stu-id="395fd-126">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
