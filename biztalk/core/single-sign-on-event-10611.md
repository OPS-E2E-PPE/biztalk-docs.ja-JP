---
title: シングル サインオン:イベント 10611 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4549ac01-b828-478f-aea0-862e14fac149
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4b0e07a7d3151cf4a25334d1d6b01fb46c3ad75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397717"
---
# <a name="single-sign-on-event-10611"></a><span data-ttu-id="d02a0-102">シングル サインオン:イベント 10611</span><span class="sxs-lookup"><span data-stu-id="d02a0-102">Single Sign-On: Event 10611</span></span>
## <a name="details"></a><span data-ttu-id="d02a0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d02a0-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d02a0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d02a0-104">Product Name</span></span>   |                                                                                                         <span data-ttu-id="d02a0-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d02a0-105">Enterprise Single Sign-On</span></span>                                                                                                         |
| <span data-ttu-id="d02a0-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d02a0-106">Product Version</span></span> |                                                                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                         |
|    <span data-ttu-id="d02a0-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d02a0-107">Event ID</span></span>     |                                                                                                                   <span data-ttu-id="d02a0-108">10611</span><span class="sxs-lookup"><span data-stu-id="d02a0-108">10611</span></span>                                                                                                                   |
|  <span data-ttu-id="d02a0-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d02a0-109">Event Source</span></span>   |                                                                                                                  <span data-ttu-id="d02a0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d02a0-110">ENTSSO</span></span>                                                                                                                   |
|    <span data-ttu-id="d02a0-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d02a0-111">Component</span></span>    |                                                                                                                    <span data-ttu-id="d02a0-112">なし</span><span class="sxs-lookup"><span data-stu-id="d02a0-112">N/A</span></span>                                                                                                                    |
|  <span data-ttu-id="d02a0-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d02a0-113">Symbolic Name</span></span>  |                                                                                                     <span data-ttu-id="d02a0-114">SSO_INFO_SERVICE_STARTING_NO_SSL</span><span class="sxs-lookup"><span data-stu-id="d02a0-114">SSO_INFO_SERVICE_STARTING_NO_SSL</span></span>                                                                                                      |
|  <span data-ttu-id="d02a0-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d02a0-115">Message Text</span></span>   | <span data-ttu-id="d02a0-116">SSO サービスが starting.%r</span><span class="sxs-lookup"><span data-stu-id="d02a0-116">The SSO service is starting.%r</span></span><br /><br /> <span data-ttu-id="d02a0-117">コンピューター名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="d02a0-117">Computer Name: %1%r</span></span><br /><br /> <span data-ttu-id="d02a0-118">SQL Server 名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="d02a0-118">SQL Server Name: %2%r</span></span><br /><br /> <span data-ttu-id="d02a0-119">SSO データベース名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="d02a0-119">SSO Database Name: %3%r</span></span><br /><br /> <span data-ttu-id="d02a0-120">SSL を使用していません。</span><span class="sxs-lookup"><span data-stu-id="d02a0-120">Not using SSL.</span></span> <span data-ttu-id="d02a0-121">SQL Server の接続をセキュリティで保護する方法の詳細についてはドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d02a0-121">See documentation for details on how to secure the SQL Server connection.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d02a0-122">説明</span><span class="sxs-lookup"><span data-stu-id="d02a0-122">Explanation</span></span>  
 <span data-ttu-id="d02a0-123">ENTSSO サービスは、Secure Sockets Layer (SSL) を使用しないで起動しています。</span><span class="sxs-lookup"><span data-stu-id="d02a0-123">The ENTSSO Service is starting without using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="d02a0-124">To SQL、SSO サービスからの接続を保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d02a0-124">It is recommended that you secure your connection from the SSO Service to SQL.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d02a0-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d02a0-125">User Action</span></span>  
 <span data-ttu-id="d02a0-126">ドキュメントを参照[SSO の SSL を有効にする方法](../core/how-to-enable-ssl-for-sso.md)</span><span class="sxs-lookup"><span data-stu-id="d02a0-126">See the documentation at [How to Enable SSL for SSO](../core/how-to-enable-ssl-for-sso.md)</span></span>  
  
 <span data-ttu-id="d02a0-127">.</span><span class="sxs-lookup"><span data-stu-id="d02a0-127">.</span></span>