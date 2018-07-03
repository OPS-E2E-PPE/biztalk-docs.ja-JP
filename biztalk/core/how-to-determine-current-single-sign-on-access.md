---
title: 現在のシングル サインオン アクセスを確認する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cab68dfc-27cd-4f7c-a0df-20c670306358
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c57cfae2c2b7545854fa7891f099a19ff7bb0098
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014771"
---
# <a name="how-to-determine-current-single-sign-on-access"></a><span data-ttu-id="25d53-102">現在のシングル サインオン アクセスを確認する方法</span><span class="sxs-lookup"><span data-stu-id="25d53-102">How to Determine Current Single Sign-On Access</span></span>
<span data-ttu-id="25d53-103">ユーザーのために実行する必要のある最初の作業の 1 つは、どの関連アプリケーションが現在のユーザーに対して設定済みであるかを判断することです。</span><span class="sxs-lookup"><span data-stu-id="25d53-103">One of the first tasks you might need to perform for a user is to determine what affiliated applications have already been set up for the current user.</span></span> <span data-ttu-id="25d53-104">この判断を行うには、ISSOMapper.GetApplications を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="25d53-104">You can perform this query with a call to ISSOMapper.GetApplications.</span></span>  
  
### <a name="to-query-the-single-sign-on-database-for-the-applications-available-to-the-current-user"></a><span data-ttu-id="25d53-105">現在のユーザーが利用可能なアプリケーションについてシングル サインオン データベースを照会するには</span><span class="sxs-lookup"><span data-stu-id="25d53-105">To query the Single Sign-On database for the applications available to the current user</span></span>  
  
1. <span data-ttu-id="25d53-106">新しいインスタンスを作成`ISSOMapper`です。</span><span class="sxs-lookup"><span data-stu-id="25d53-106">Create a new instance of `ISSOMapper`.</span></span>  
  
    <span data-ttu-id="25d53-107">`ISSOMapper` はシングル サインオン (SSO) から情報を取得するために設計されたインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="25d53-107">In general, `ISSOMapper` is an interface designed to retrieve information from Single Sign-On (SSO).</span></span> <span data-ttu-id="25d53-108">同様な照会を行う場合は、`ISSOMapper` を使用するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="25d53-108">You will most likely use `ISSOMapper` in many similar queries.</span></span>  
  
2. <span data-ttu-id="25d53-109">GetApplications を呼び出して、現在のユーザーに関連するアプリケーションをすべて取得します。</span><span class="sxs-lookup"><span data-stu-id="25d53-109">Retrieve all applications that are affiliated with the current user by calling GetApplications.</span></span>  
  
    <span data-ttu-id="25d53-110">GetApplications は、自動的に、現在のユーザーに関連するアプリケーションのみを返します。</span><span class="sxs-lookup"><span data-stu-id="25d53-110">GetApplications automatically returns only the affiliated applications of the current user.</span></span>  
  
   <span data-ttu-id="25d53-111">次のコード例は、シングル サインオン データベースを照会する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="25d53-111">The following code example demonstrates how to query the Single Sign-On database.</span></span>  
  
```  
private static string[] Applications=null;  
. . .  
public static string[] GetCurrentUserApplications()  
{  
   if(Applications==null)  
   {  
      string[] descs;  
      string[] contacts;  
      ISSOMapper mapper=new ISSOMapper();  
      mapper.GetApplications(out Applications, out descs, out contacts);  
   }  
   return Applications;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="25d53-112">参照</span><span class="sxs-lookup"><span data-stu-id="25d53-112">See Also</span></span>  
 [<span data-ttu-id="25d53-113">Enterprise Single Sign-On によるプログラミング</span><span class="sxs-lookup"><span data-stu-id="25d53-113">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)