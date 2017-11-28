---
title: "現在のシングル サインオン アクセスを確認する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cab68dfc-27cd-4f7c-a0df-20c670306358
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b16fc1d1677fa1a8859c75b43be36de9209dbac0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-determine-current-single-sign-on-access"></a><span data-ttu-id="cd0a0-102">現在のシングル サインオン アクセスを確認する方法</span><span class="sxs-lookup"><span data-stu-id="cd0a0-102">How to Determine Current Single Sign-On Access</span></span>
<span data-ttu-id="cd0a0-103">ユーザーのために実行する必要のある最初の作業の 1 つは、どの関連アプリケーションが現在のユーザーに対して設定済みであるかを判断することです。</span><span class="sxs-lookup"><span data-stu-id="cd0a0-103">One of the first tasks you might need to perform for a user is to determine what affiliated applications have already been set up for the current user.</span></span> <span data-ttu-id="cd0a0-104">この判断を行うには、ISSOMapper.GetApplications を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cd0a0-104">You can perform this query with a call to ISSOMapper.GetApplications.</span></span>  
  
### <a name="to-query-the-single-sign-on-database-for-the-applications-available-to-the-current-user"></a><span data-ttu-id="cd0a0-105">現在のユーザーが利用可能なアプリケーションについてシングル サインオン データベースを照会するには</span><span class="sxs-lookup"><span data-stu-id="cd0a0-105">To query the Single Sign-On database for the applications available to the current user</span></span>  
  
1.  <span data-ttu-id="cd0a0-106">新しいインスタンスを作成する`ISSOMapper`です。</span><span class="sxs-lookup"><span data-stu-id="cd0a0-106">Create a new instance of `ISSOMapper`.</span></span>  
  
     <span data-ttu-id="cd0a0-107">`ISSOMapper` はシングル サインオン (SSO) から情報を取得するために設計されたインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="cd0a0-107">In general, `ISSOMapper` is an interface designed to retrieve information from Single Sign-On (SSO).</span></span> <span data-ttu-id="cd0a0-108">同様な照会を行う場合は、`ISSOMapper` を使用するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="cd0a0-108">You will most likely use `ISSOMapper` in many similar queries.</span></span>  
  
2.  <span data-ttu-id="cd0a0-109">GetApplications を呼び出して、現在のユーザーに関連するアプリケーションをすべて取得します。</span><span class="sxs-lookup"><span data-stu-id="cd0a0-109">Retrieve all applications that are affiliated with the current user by calling GetApplications.</span></span>  
  
     <span data-ttu-id="cd0a0-110">GetApplications は、自動的に、現在のユーザーに関連するアプリケーションのみを返します。</span><span class="sxs-lookup"><span data-stu-id="cd0a0-110">GetApplications automatically returns only the affiliated applications of the current user.</span></span>  
  
 <span data-ttu-id="cd0a0-111">次のコード例は、シングル サインオン データベースを照会する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="cd0a0-111">The following code example demonstrates how to query the Single Sign-On database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cd0a0-112">参照</span><span class="sxs-lookup"><span data-stu-id="cd0a0-112">See Also</span></span>  
 [<span data-ttu-id="cd0a0-113">エンタープライズ シングル サインオンを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="cd0a0-113">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)