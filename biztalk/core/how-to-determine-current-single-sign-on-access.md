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
ms.openlocfilehash: 781fde1a4b7af82c851fb80a9df32a6eb93d8ce7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338586"
---
# <a name="how-to-determine-current-single-sign-on-access"></a><span data-ttu-id="f05ff-102">現在のシングル サインオン アクセスを確認する方法</span><span class="sxs-lookup"><span data-stu-id="f05ff-102">How to Determine Current Single Sign-On Access</span></span>
<span data-ttu-id="f05ff-103">ユーザーに対して実行する必要があります最初のタスクの 1 つは、どのような関連アプリケーションが既に設定されて現在のユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="f05ff-103">One of the first tasks you might need to perform for a user is to determine what affiliated applications have already been set up for the current user.</span></span> <span data-ttu-id="f05ff-104">ISSOMapper.GetApplications への呼び出しでは、このクエリを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f05ff-104">You can perform this query with a call to ISSOMapper.GetApplications.</span></span>  
  
### <a name="to-query-the-single-sign-on-database-for-the-applications-available-to-the-current-user"></a><span data-ttu-id="f05ff-105">現在のユーザーに使用可能なアプリケーションのシングル サインオン データベースに照会するには</span><span class="sxs-lookup"><span data-stu-id="f05ff-105">To query the Single Sign-On database for the applications available to the current user</span></span>  
  
1. <span data-ttu-id="f05ff-106">新しいインスタンスを作成`ISSOMapper`です。</span><span class="sxs-lookup"><span data-stu-id="f05ff-106">Create a new instance of `ISSOMapper`.</span></span>  
  
    <span data-ttu-id="f05ff-107">一般に、`ISSOMapper`はからシングル サインオン (SSO) の情報を取得するためのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="f05ff-107">In general, `ISSOMapper` is an interface designed to retrieve information from Single Sign-On (SSO).</span></span> <span data-ttu-id="f05ff-108">使用するほとんどの場合`ISSOMapper`で同様な照会します。</span><span class="sxs-lookup"><span data-stu-id="f05ff-108">You will most likely use `ISSOMapper` in many similar queries.</span></span>  
  
2. <span data-ttu-id="f05ff-109">GetApplications を呼び出して、現在のユーザーに関連しているすべてのアプリケーションを取得します。</span><span class="sxs-lookup"><span data-stu-id="f05ff-109">Retrieve all applications that are affiliated with the current user by calling GetApplications.</span></span>  
  
    <span data-ttu-id="f05ff-110">GetApplications は、自動的に現在のユーザーの関連アプリケーションのみを返します。</span><span class="sxs-lookup"><span data-stu-id="f05ff-110">GetApplications automatically returns only the affiliated applications of the current user.</span></span>  
  
   <span data-ttu-id="f05ff-111">次のコード例では、シングル サインオン データベースに照会する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f05ff-111">The following code example demonstrates how to query the Single Sign-On database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f05ff-112">参照</span><span class="sxs-lookup"><span data-stu-id="f05ff-112">See Also</span></span>  
 [<span data-ttu-id="f05ff-113">Enterprise Single Sign-On によるプログラミング</span><span class="sxs-lookup"><span data-stu-id="f05ff-113">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)