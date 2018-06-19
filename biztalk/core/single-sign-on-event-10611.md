---
title: 'シングル サインオン: イベント 10611 |Microsoft ドキュメント'
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
ms.openlocfilehash: 3582ee070b960b7eb17facc8d48e0b3e11dc5b9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270418"
---
# <a name="single-sign-on-event-10611"></a><span data-ttu-id="6469e-102">シングル サインオン: イベント 10611</span><span class="sxs-lookup"><span data-stu-id="6469e-102">Single Sign-On: Event 10611</span></span>
## <a name="details"></a><span data-ttu-id="6469e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6469e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6469e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6469e-104">Product Name</span></span>|<span data-ttu-id="6469e-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6469e-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="6469e-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6469e-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="6469e-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6469e-107">Event ID</span></span>|<span data-ttu-id="6469e-108">10611</span><span class="sxs-lookup"><span data-stu-id="6469e-108">10611</span></span>|  
|<span data-ttu-id="6469e-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6469e-109">Event Source</span></span>|<span data-ttu-id="6469e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6469e-110">ENTSSO</span></span>|  
|<span data-ttu-id="6469e-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6469e-111">Component</span></span>|<span data-ttu-id="6469e-112">なし</span><span class="sxs-lookup"><span data-stu-id="6469e-112">N/A</span></span>|  
|<span data-ttu-id="6469e-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6469e-113">Symbolic Name</span></span>|<span data-ttu-id="6469e-114">SSO_INFO_SERVICE_STARTING_NO_SSL</span><span class="sxs-lookup"><span data-stu-id="6469e-114">SSO_INFO_SERVICE_STARTING_NO_SSL</span></span>|  
|<span data-ttu-id="6469e-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6469e-115">Message Text</span></span>|<span data-ttu-id="6469e-116">SSO サービスが開始しました。%r</span><span class="sxs-lookup"><span data-stu-id="6469e-116">The SSO service is starting.%r</span></span><br /><br /> <span data-ttu-id="6469e-117">コンピューター名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="6469e-117">Computer Name: %1%r</span></span><br /><br /> <span data-ttu-id="6469e-118">SQL Server 名: %2 %r</span><span class="sxs-lookup"><span data-stu-id="6469e-118">SQL Server Name: %2%r</span></span><br /><br /> <span data-ttu-id="6469e-119">SSO データベース名: %3 %r</span><span class="sxs-lookup"><span data-stu-id="6469e-119">SSO Database Name: %3%r</span></span><br /><br /> <span data-ttu-id="6469e-120">SSL を使用していません。</span><span class="sxs-lookup"><span data-stu-id="6469e-120">Not using SSL.</span></span> <span data-ttu-id="6469e-121">SQL Server の接続をセキュリティで保護する方法については、ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6469e-121">See documentation for details on how to secure the SQL Server connection.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6469e-122">説明</span><span class="sxs-lookup"><span data-stu-id="6469e-122">Explanation</span></span>  
 <span data-ttu-id="6469e-123">ENTSSO サービスは SSL (Secure Sockets Layer) を使用せずに開始されています。</span><span class="sxs-lookup"><span data-stu-id="6469e-123">The ENTSSO Service is starting without using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="6469e-124">SSO サービスから SQL への接続をセキュリティで保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6469e-124">It is recommended that you secure your connection from the SSO Service to SQL.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6469e-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6469e-125">User Action</span></span>  
 <span data-ttu-id="6469e-126">マニュアルを参照して[SSO の SSL を有効にする方法](../core/how-to-enable-ssl-for-sso.md)</span><span class="sxs-lookup"><span data-stu-id="6469e-126">See the documentation at [How to Enable SSL for SSO](../core/how-to-enable-ssl-for-sso.md)</span></span>  
  
 <span data-ttu-id="6469e-127">のインスタンスにアクセスするたびに SQL Server ログインを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6469e-127">.</span></span>