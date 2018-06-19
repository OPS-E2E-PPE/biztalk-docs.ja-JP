---
title: 作成し、アプリケーションでのシングル サインオンを記述する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d717885-b132-4ba0-a93b-03377ac5eb97
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 423439795d9a3822427edbee2e062c3c0aa6bb80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249090"
---
# <a name="how-to-create-and-describe-an-application-to-single-sign-on"></a><span data-ttu-id="fb2d5-102">作成し、アプリケーションでのシングル サインオンを記述する方法</span><span class="sxs-lookup"><span data-stu-id="fb2d5-102">How to Create and Describe an Application to Single Sign-On</span></span>
<span data-ttu-id="fb2d5-103">一般的な管理タスクとして、関連アプリケーションをエンタープライズ シングル サインオン (SSO) データベースに追加することが挙げられます。</span><span class="sxs-lookup"><span data-stu-id="fb2d5-103">A common administrative task that you might need to perform is adding an affiliate application into the Enterprise Single Sign-On (SSO) database.</span></span> <span data-ttu-id="fb2d5-104">関連アプリケーションをエンタープライズ SSO データベースに追加することによって、ユーザーおよび資格情報を関連アプリケーションに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="fb2d5-104">Adding an affiliate application to the Enterprise SSO database enables you to associate users and credentials with the affiliated application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb2d5-105">関連アプリケーションを作成するには、"SSO 関連管理者" 以上の権限を持つアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="fb2d5-105">Creating an affiliated application requires membership in the "SSO Affiliate Administrator" account or above.</span></span>  
  
### <a name="to-create-and-describe-an-application-in-the-sso-database"></a><span data-ttu-id="fb2d5-106">SSO データベースに対してアプリケーションを作成および記述するには</span><span class="sxs-lookup"><span data-stu-id="fb2d5-106">To create and describe an application in the SSO database</span></span>  
  
1.  <span data-ttu-id="fb2d5-107">`ISSOAdmin` オブジェクトを新規作成します。</span><span class="sxs-lookup"><span data-stu-id="fb2d5-107">Create a new `ISSOAdmin` object.</span></span>  
  
2.  <span data-ttu-id="fb2d5-108">`ISSOAdmin.CreateApplication` を呼び出し、新しいアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb2d5-108">Create a new application with a call to `ISSOAdmin.CreateApplication`.</span></span>  
  
3.  <span data-ttu-id="fb2d5-109">`ISSOAdmin.CreateFieldInfo` を呼び出し、アプリケーションについて記述するフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="fb2d5-109">Add the relevant fields describing the application with a call to `ISSOAdmin.CreateFieldInfo`.</span></span>  
  
     <span data-ttu-id="fb2d5-110">この手順で、アプリケーションのユーザーとパスワードがデータベースに伝達されます。</span><span class="sxs-lookup"><span data-stu-id="fb2d5-110">During this step, you tell the database that an application has users and associated passwords.</span></span>  
  
4.  <span data-ttu-id="fb2d5-111">`ISSOAdmin.UpdateApplication` または `ISSOAdmin2.UpdateApplication2` を呼び出し、新たに作成された情報をサーバーにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="fb2d5-111">Push the newly created description out to the server with a call to `ISSOAdmin.UpdateApplication` or `ISSOAdmin2.UpdateApplication2`.</span></span>  
  
     <span data-ttu-id="fb2d5-112">この 2 つのメソッドの違いは、アプリケーションの更新を記述する際の手段にあります。`UpdateApplication2` では `IPropertyBag` が使用されるのに対し、`UpdateApplication` では複数のパラメーターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb2d5-112">The difference between the two methods is that `UpdateApplication2` uses an `IPropertyBag` as the way to describe the application updates, while `UpdateApplication` has multiple parameters.</span></span>  
  
5.  <span data-ttu-id="fb2d5-113">`ISSOAdmin.PurgeCacheForApplication` を呼び出して、変更内容のローカル キャッシュを削除します。</span><span class="sxs-lookup"><span data-stu-id="fb2d5-113">Purge the local cache for the changes you made by calling `ISSOAdmin.PurgeCacheForApplication`.</span></span>  
  
     <span data-ttu-id="fb2d5-114">ローカル キャッシュはセキュリティ上、決して安全な場所ではありません。手順 3. で記述した名前とパスワードを、ローカル キャッシュから確実に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb2d5-114">Purging the local cache is a security measure that prevents having the names and passwords that you describe in step 3 to exist in an unsecured location.</span></span>  
  
 <span data-ttu-id="fb2d5-115">次の例は、アプリケーションを作成して、フィールド情報を追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fb2d5-115">The following example shows how to create an application and add field information.</span></span>  
  
```  
public static bool AddApplication(string name, string admins, string users)  
    {  
       try  
       {  
          ISSOAdmin admin=new ISSOAdmin();  
          // Create application.  
          admin.CreateApplication(name, "SSO Sample Application", "administrator@ssoaffiliateapplication.com", users, admins, SSOFlag.SSO_WINDOWS_TO_EXTERNAL | SSOFlag.SSO_FLAG_ALLOW_TICKETS | SSOFlag.SSO_FLAG_VALIDATE_TICKETS, 2);  
          // Add fields.  
          admin.CreateFieldInfo(name, "User Id", SSOFlag.SSO_FLAG_NONE);  
          admin.CreateFieldInfo(name, "Password", SSOFlag.SSO_FLAG_FIELD_INFO_MASK);  
          // Enable application.  
          admin.UpdateApplication(name, null, null, null, null, SSOFlag.SSO_FLAG_ENABLED, SSOFlag.SSO_FLAG_ENABLED);  
          // Purge changes.  
          admin.PurgeCacheForApplication(name);  
       }  
       catch  
       {  
          return false;  
       }  
       return true;  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb2d5-116">参照</span><span class="sxs-lookup"><span data-stu-id="fb2d5-116">See Also</span></span>  
 [<span data-ttu-id="fb2d5-117">エンタープライズ シングル サインオンを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="fb2d5-117">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)