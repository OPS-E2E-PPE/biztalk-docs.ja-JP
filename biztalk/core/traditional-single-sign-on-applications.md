---
title: 従来のシングル サインオン アプリケーション |Microsoft Docs
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
ms.openlocfilehash: 75ffc09f49e6fecc1d6773a3b5ea8e89f8d98ea6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313324"
---
# <a name="traditional-single-sign-on-applications"></a><span data-ttu-id="2670a-102">従来のシングル サインオン アプリケーション</span><span class="sxs-lookup"><span data-stu-id="2670a-102">Traditional Single Sign-On Applications</span></span>
<span data-ttu-id="2670a-103">シングル サインオン (SSO) プログラミング アーキテクチャには、アプリケーションとユーザー、参照コンポーネントを指定した使用するための資格情報を参照および管理タスクを実行する管理コンポーネント間をマップするマッピング コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2670a-103">The Single Sign-On (SSO) programming architecture contains a mapping component to map between applications and users, a lookup component to look up credentials for a specified use, and an administration component to perform administrative tasks.</span></span> <span data-ttu-id="2670a-104">さらに、アプリケーションを発行してチケットを引き換えるように SSO にはによってチケット インターフェイスも含まれます。</span><span class="sxs-lookup"><span data-stu-id="2670a-104">In addition, SSO also contains a ticketing interface so that your application can issue and redeem tickets.</span></span>  
  
## <a name="mapping"></a><span data-ttu-id="2670a-105">マッピング</span><span class="sxs-lookup"><span data-stu-id="2670a-105">Mapping</span></span>  
 <span data-ttu-id="2670a-106">マッピングは、指定したアプリケーションが指定されたユーザーをリンクするプロセスです。</span><span class="sxs-lookup"><span data-stu-id="2670a-106">Mapping is the process of linking a specified user with a specified application.</span></span> <span data-ttu-id="2670a-107">関連アプリケーションとを使用しているユーザーどうしをマップできる`ISSOMapping`、 `ISSOMapper`、および`ISSOMapper2`します。</span><span class="sxs-lookup"><span data-stu-id="2670a-107">You can map between affiliate applications and users who are using `ISSOMapping`, `ISSOMapper`, and `ISSOMapper2`.</span></span> <span data-ttu-id="2670a-108">`ISSOMapping`、作成、削除、有効にする、およびマッピングを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2670a-108">With `ISSOMapping`, you can create, delete, enable, and disable mappings.</span></span> <span data-ttu-id="2670a-109">`ISSOMapper`、および`ISSOMapper2`を取得し、現在のユーザーのデータのマッピングを設定できます。</span><span class="sxs-lookup"><span data-stu-id="2670a-109">With `ISSOMapper`, and `ISSOMapper2`, you can get and set mapping data for the current user.</span></span>  
  
## <a name="lookup"></a><span data-ttu-id="2670a-110">Lookup</span><span class="sxs-lookup"><span data-stu-id="2670a-110">Lookup</span></span>  
 <span data-ttu-id="2670a-111">シングル サインオンのプログラミング インターフェイスのコアは、指定されたユーザーの資格情報を検索する機能です。</span><span class="sxs-lookup"><span data-stu-id="2670a-111">The core of the Single Sign-On programming interface is the ability to look up credentials for specified users.</span></span> <span data-ttu-id="2670a-112">使用して資格情報を調べることができます`ISSOLookup1`、および`ISSOLookup2`します。</span><span class="sxs-lookup"><span data-stu-id="2670a-112">You can look up credentials using `ISSOLookup1`, and `ISSOLookup2`.</span></span> <span data-ttu-id="2670a-113">`ISSOLookup1`、、ユーザーが自身の外部資格情報を取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2670a-113">`ISSOLookup1`, enables the user to retrieve their own external credentials.</span></span> <span data-ttu-id="2670a-114">これに対し、`ISSOLookup2`ローカルの関連アプリケーションに関するリモート ユーザーの資格情報を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="2670a-114">In contrast, `ISSOLookup2` also enables you to look up the credentials of a remote user for a local affiliate application.</span></span> <span data-ttu-id="2670a-115">前者は従来のシングル サインオン アプリケーションに必要なのに対し、後者は便利なホスト側開始シングル サインオン アプリケーションを記述するとき。</span><span class="sxs-lookup"><span data-stu-id="2670a-115">The former is necessary for a traditional Single Sign-On application, whereas the latter is useful when you are writing a host-initiated Single Sign-On application.</span></span>  
  
## <a name="administration"></a><span data-ttu-id="2670a-116">管理</span><span class="sxs-lookup"><span data-stu-id="2670a-116">Administration</span></span>  
 <span data-ttu-id="2670a-117">プログラムにより、管理機能の多くを行うことができます`ISSOAdmin`、 `ISSOAdmin2`、および`ISSOConfigStore`します。</span><span class="sxs-lookup"><span data-stu-id="2670a-117">You can perform many of the administrative capabilities programmatically through `ISSOAdmin`, `ISSOAdmin2`, and `ISSOConfigStore`.</span></span> <span data-ttu-id="2670a-118">このようなタスクには、シングル サインオンの構成の作成と、アプリケーションにシングル サインオンについて説明が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2670a-118">Such tasks include configuring Single Sign-On and creating and describing an application to Single Sign-On.</span></span> <span data-ttu-id="2670a-119">作成して変更を使用して SSO データベース`ISSOConfigDB`、 `ISSOConfigOM`、および`ISSOConfigSS`します。</span><span class="sxs-lookup"><span data-stu-id="2670a-119">You also can create and modify SSO databases using `ISSOConfigDB`, `ISSOConfigOM`, and `ISSOConfigSS`.</span></span> <span data-ttu-id="2670a-120">使用してパスワード同期機能を管理する最後に、`ISSOPSAdmin`します。</span><span class="sxs-lookup"><span data-stu-id="2670a-120">Finally, you can administer the password sync features using `ISSOPSAdmin`.</span></span>  
  
## <a name="communication-and-ticketing"></a><span data-ttu-id="2670a-121">通信とチケット</span><span class="sxs-lookup"><span data-stu-id="2670a-121">Communication and Ticketing</span></span>  
 <span data-ttu-id="2670a-122">ユーザーがリモート アプリケーションと通信できるように多くの場合、アプリケーションがメッセージを発行します。</span><span class="sxs-lookup"><span data-stu-id="2670a-122">Your application will most likely issue messages so that your user can communicate with a remote application.</span></span> <span data-ttu-id="2670a-123">リモート アプリケーションをより安全に通信するには、は、発行し、シングル サインオン チケットを引き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="2670a-123">To communicate with a remote application more securely, you must issue and redeem a Single Sign-On ticket.</span></span> <span data-ttu-id="2670a-124">発行し、チケットを引き換えるにプログラムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2670a-124">You can also issue and redeem tickets programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2670a-125">参照</span><span class="sxs-lookup"><span data-stu-id="2670a-125">See Also</span></span>  
 [<span data-ttu-id="2670a-126">シングル サインオン アプリケーション</span><span class="sxs-lookup"><span data-stu-id="2670a-126">Single Sign-On Applications</span></span>](../core/single-sign-on-applications.md)