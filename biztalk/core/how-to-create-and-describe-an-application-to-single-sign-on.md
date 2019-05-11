---
title: 作成して、シングル サインオンにアプリケーションを記述する方法 |Microsoft Docs
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
ms.openlocfilehash: 9b914cc54e48aaa4a58d3f370f50132265f97def
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385517"
---
# <a name="how-to-create-and-describe-an-application-to-single-sign-on"></a><span data-ttu-id="c0ce1-102">作成して、シングル サインオンにアプリケーションを記述する方法</span><span class="sxs-lookup"><span data-stu-id="c0ce1-102">How to Create and Describe an Application to Single Sign-On</span></span>
<span data-ttu-id="c0ce1-103">一般的な管理タスクを実行する必要がありますが、エンタープライズ シングル サインオン (SSO) データベースに関連アプリケーションを追加しています。</span><span class="sxs-lookup"><span data-stu-id="c0ce1-103">A common administrative task that you might need to perform is adding an affiliate application into the Enterprise Single Sign-On (SSO) database.</span></span> <span data-ttu-id="c0ce1-104">関連アプリケーション、エンタープライズ SSO データベースを追加するには、ユーザーと資格情報関連のアプリケーションに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c0ce1-104">Adding an affiliate application to the Enterprise SSO database enables you to associate users and credentials with the affiliated application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0ce1-105">関連アプリケーションを作成するには、「SSO 関連管理者」アカウントまたはの上のメンバーシップが必要です。</span><span class="sxs-lookup"><span data-stu-id="c0ce1-105">Creating an affiliated application requires membership in the "SSO Affiliate Administrator" account or above.</span></span>  
  
### <a name="to-create-and-describe-an-application-in-the-sso-database"></a><span data-ttu-id="c0ce1-106">作成し、SSO データベース内のアプリケーションを記述するには</span><span class="sxs-lookup"><span data-stu-id="c0ce1-106">To create and describe an application in the SSO database</span></span>  
  
1. <span data-ttu-id="c0ce1-107">新規作成`ISSOAdmin`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c0ce1-107">Create a new `ISSOAdmin` object.</span></span>  
  
2. <span data-ttu-id="c0ce1-108">呼び出して、新しいアプリケーションを作成`ISSOAdmin.CreateApplication`です。</span><span class="sxs-lookup"><span data-stu-id="c0ce1-108">Create a new application with a call to `ISSOAdmin.CreateApplication`.</span></span>  
  
3. <span data-ttu-id="c0ce1-109">呼び出しを使用してアプリケーションを記述するフィールドを追加`ISSOAdmin.CreateFieldInfo`します。</span><span class="sxs-lookup"><span data-stu-id="c0ce1-109">Add the relevant fields describing the application with a call to `ISSOAdmin.CreateFieldInfo`.</span></span>  
  
    <span data-ttu-id="c0ce1-110">この手順では、中にすることを伝えるデータベース アプリケーション ユーザーと関連付けられているパスワード。</span><span class="sxs-lookup"><span data-stu-id="c0ce1-110">During this step, you tell the database that an application has users and associated passwords.</span></span>  
  
4. <span data-ttu-id="c0ce1-111">呼び出しを使用して、サーバーを新しく作成された説明にプッシュ`ISSOAdmin.UpdateApplication`または`ISSOAdmin2.UpdateApplication2`します。</span><span class="sxs-lookup"><span data-stu-id="c0ce1-111">Push the newly created description out to the server with a call to `ISSOAdmin.UpdateApplication` or `ISSOAdmin2.UpdateApplication2`.</span></span>  
  
    <span data-ttu-id="c0ce1-112">2 つのメソッド間の差は`UpdateApplication2`を使用して、`IPropertyBag`中にアプリケーションを記述する方法は、更新、`UpdateApplication`は複数のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="c0ce1-112">The difference between the two methods is that `UpdateApplication2` uses an `IPropertyBag` as the way to describe the application updates, while `UpdateApplication` has multiple parameters.</span></span>  
  
5. <span data-ttu-id="c0ce1-113">呼び出すことによって行われた変更のローカル キャッシュを消去`ISSOAdmin.PurgeCacheForApplication`します。</span><span class="sxs-lookup"><span data-stu-id="c0ce1-113">Purge the local cache for the changes you made by calling `ISSOAdmin.PurgeCacheForApplication`.</span></span>  
  
    <span data-ttu-id="c0ce1-114">名とパスワードを安全な場所に存在する 3 の手順で説明することによってのセキュリティ対策は、ローカル キャッシュを消去します。</span><span class="sxs-lookup"><span data-stu-id="c0ce1-114">Purging the local cache is a security measure that prevents having the names and passwords that you describe in step 3 to exist in an unsecured location.</span></span>  
  
   <span data-ttu-id="c0ce1-115">次の例では、アプリケーションを作成し、フィールドの情報を追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c0ce1-115">The following example shows how to create an application and add field information.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c0ce1-116">参照</span><span class="sxs-lookup"><span data-stu-id="c0ce1-116">See Also</span></span>  
 [<span data-ttu-id="c0ce1-117">Enterprise Single Sign-On によるプログラミング</span><span class="sxs-lookup"><span data-stu-id="c0ce1-117">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)