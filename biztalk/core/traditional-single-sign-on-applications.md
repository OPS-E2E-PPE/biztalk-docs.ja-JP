---
title: 従来シングル サインオン アプリケーション |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a49bdae7-215a-43fb-875e-f64abb37aef0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4396ecfab477fe1ae17b1abbb09ebf71c9bcb58c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279690"
---
# <a name="traditional-single-sign-on-applications"></a><span data-ttu-id="477df-102">従来シングル サインオン アプリケーション</span><span class="sxs-lookup"><span data-stu-id="477df-102">Traditional Single Sign-On Applications</span></span>
<span data-ttu-id="477df-103">シングル サインオン (SSO) のプログラミング アーキテクチャには、アプリケーションとユーザー間でマップするためのマッピング コンポーネント、特定の用途の資格情報を参照するための参照コンポーネント、および管理タスクを実行するための管理コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="477df-103">The Single Sign-On (SSO) programming architecture contains a mapping component to map between applications and users, a lookup component to look up credentials for a specified use, and an administration component to perform administrative tasks.</span></span> <span data-ttu-id="477df-104">さらに、SSO にはアプリケーションがチケットを発行および引き換えるためのチケット インターフェイスも含まれています。</span><span class="sxs-lookup"><span data-stu-id="477df-104">In addition, SSO also contains a ticketing interface so that your application can issue and redeem tickets.</span></span>  
  
## <a name="mapping"></a><span data-ttu-id="477df-105">マッピング</span><span class="sxs-lookup"><span data-stu-id="477df-105">Mapping</span></span>  
 <span data-ttu-id="477df-106">マッピングは、特定のユーザーを特定のアプリケーションにリンクするプロセスです。</span><span class="sxs-lookup"><span data-stu-id="477df-106">Mapping is the process of linking a specified user with a specified application.</span></span> <span data-ttu-id="477df-107">関連アプリケーションと、`ISSOMapping`、`ISSOMapper`、および `ISSOMapper2` を使用しているユーザーの間をマップできます。</span><span class="sxs-lookup"><span data-stu-id="477df-107">You can map between affiliate applications and users who are using `ISSOMapping`, `ISSOMapper`, and `ISSOMapper2`.</span></span> <span data-ttu-id="477df-108">`ISSOMapping` では、マッピングの作成、削除、有効化、および無効化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="477df-108">With `ISSOMapping`, you can create, delete, enable, and disable mappings.</span></span> <span data-ttu-id="477df-109">`ISSOMapper` および `ISSOMapper2` では、現在のユーザーのマッピング データの取得や設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="477df-109">With `ISSOMapper`, and `ISSOMapper2`, you can get and set mapping data for the current user.</span></span>  
  
## <a name="lookup"></a><span data-ttu-id="477df-110">Lookup</span><span class="sxs-lookup"><span data-stu-id="477df-110">Lookup</span></span>  
 <span data-ttu-id="477df-111">シングル サインオンのプログラミング インターフェイスの中心となるのは、特定のユーザーの資格情報を参照する機能です。</span><span class="sxs-lookup"><span data-stu-id="477df-111">The core of the Single Sign-On programming interface is the ability to look up credentials for specified users.</span></span> <span data-ttu-id="477df-112">`ISSOLookup1` および `ISSOLookup2` を使用して資格情報を参照できます。</span><span class="sxs-lookup"><span data-stu-id="477df-112">You can look up credentials using `ISSOLookup1`, and `ISSOLookup2`.</span></span> <span data-ttu-id="477df-113">`ISSOLookup1` では、独自の外部資格情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="477df-113">`ISSOLookup1`, enables the user to retrieve their own external credentials.</span></span> <span data-ttu-id="477df-114">これに対して `ISSOLookup2` では、ローカルの関連アプリケーションに関するリモート ユーザーの資格情報を参照できます。</span><span class="sxs-lookup"><span data-stu-id="477df-114">In contrast, `ISSOLookup2` also enables you to look up the credentials of a remote user for a local affiliate application.</span></span> <span data-ttu-id="477df-115">前者は、従来のシングル サインオン アプリケーションに必要であり、後者は、ホスト側開始のシングル サインオン アプリケーションを記述するときに便利です。</span><span class="sxs-lookup"><span data-stu-id="477df-115">The former is necessary for a traditional Single Sign-On application, whereas the latter is useful when you are writing a host-initiated Single Sign-On application.</span></span>  
  
## <a name="administration"></a><span data-ttu-id="477df-116">管理</span><span class="sxs-lookup"><span data-stu-id="477df-116">Administration</span></span>  
 <span data-ttu-id="477df-117">`ISSOAdmin`、`ISSOAdmin2`、および `ISSOConfigStore` を使用すると、管理機能の多くをプログラムで実行できます。</span><span class="sxs-lookup"><span data-stu-id="477df-117">You can perform many of the administrative capabilities programmatically through `ISSOAdmin`, `ISSOAdmin2`, and `ISSOConfigStore`.</span></span> <span data-ttu-id="477df-118">実行できるタスクは、シングル サインオンの構成や、シングル サインオンに対するアプリケーションの作成および記述です。</span><span class="sxs-lookup"><span data-stu-id="477df-118">Such tasks include configuring Single Sign-On and creating and describing an application to Single Sign-On.</span></span> <span data-ttu-id="477df-119">また、`ISSOConfigDB`、`ISSOConfigOM`、および `ISSOConfigSS` を使用して、SSO データベースを作成し、変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="477df-119">You also can create and modify SSO databases using `ISSOConfigDB`, `ISSOConfigOM`, and `ISSOConfigSS`.</span></span> <span data-ttu-id="477df-120">`ISSOPSAdmin` ではパスワード同期機能を管理できます。</span><span class="sxs-lookup"><span data-stu-id="477df-120">Finally, you can administer the password sync features using `ISSOPSAdmin`.</span></span>  
  
## <a name="communication-and-ticketing"></a><span data-ttu-id="477df-121">通信とチケット</span><span class="sxs-lookup"><span data-stu-id="477df-121">Communication and Ticketing</span></span>  
 <span data-ttu-id="477df-122">アプリケーションでは、一般に、ユーザーがリモート アプリケーションと通信できるようにメッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="477df-122">Your application will most likely issue messages so that your user can communicate with a remote application.</span></span> <span data-ttu-id="477df-123">リモート アプリケーションとより安全に通信するには、シングル サインオン チケットを発行して引き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="477df-123">To communicate with a remote application more securely, you must issue and redeem a Single Sign-On ticket.</span></span> <span data-ttu-id="477df-124">発行し、チケットを引き換えるにプログラムによってもします。</span><span class="sxs-lookup"><span data-stu-id="477df-124">You can also issue and redeem tickets programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="477df-125">参照</span><span class="sxs-lookup"><span data-stu-id="477df-125">See Also</span></span>  
 [<span data-ttu-id="477df-126">シングル サインオン アプリケーション</span><span class="sxs-lookup"><span data-stu-id="477df-126">Single Sign-On Applications</span></span>](../core/single-sign-on-applications.md)