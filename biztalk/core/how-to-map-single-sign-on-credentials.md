---
title: シングル サインオン資格情報をマップする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e847bde9-7a4c-4b81-8ad6-6a7cf23d19a1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a95a56da0d30ec0f30c556dcab01b3789f3e1fb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336268"
---
# <a name="how-to-map-single-sign-on-credentials"></a><span data-ttu-id="958be-102">シングル サインオン資格情報をマップする方法</span><span class="sxs-lookup"><span data-stu-id="958be-102">How to Map Single Sign-On Credentials</span></span>
<span data-ttu-id="958be-103">エンタープライズ シングル サインオン データベースに関連があるアプリケーションの場合は、そのアプリケーションにユーザーの資格情報をマップできます。</span><span class="sxs-lookup"><span data-stu-id="958be-103">When you know that you have affiliated applications in your Enterprise Single Sign-On database, you can map the credentials for a user to that application.</span></span> <span data-ttu-id="958be-104">関連アプリケーションへの現在のユーザーの資格情報のマッピングの組み合わせを使用することが必要です、`ISSOMapper`と`ISSOMapping`インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="958be-104">Mapping the credentials of the current user to an affiliated application requires that you use a combination of the `ISSOMapper` and `ISSOMapping` interfaces.</span></span>  
  
### <a name="to-map-between-an-affiliated-application-and-user-credentials"></a><span data-ttu-id="958be-105">関連アプリケーションとユーザーの資格情報の間にマップするには</span><span class="sxs-lookup"><span data-stu-id="958be-105">To map between an affiliated application and user credentials</span></span>  
  
1. <span data-ttu-id="958be-106">新しいインスタンスを作成`ISSOMapper`と`ISSOMapping`します。</span><span class="sxs-lookup"><span data-stu-id="958be-106">Create new instances of `ISSOMapper` and `ISSOMapping`.</span></span>  
  
2. <span data-ttu-id="958be-107">設定、`ISSOMapping`プロパティを関連する値。</span><span class="sxs-lookup"><span data-stu-id="958be-107">Set the `ISSOMapping` properties to the relevant values.</span></span>  
  
    <span data-ttu-id="958be-108">関連するプロパティを`ISSOMapping`はユーザーの Microsoft Windows ドメイン名、Windows ユーザー名、関連のアプリケーションの名前、および外部ユーザー名。</span><span class="sxs-lookup"><span data-stu-id="958be-108">The relevant properties for `ISSOMapping` are the Microsoft Windows domain name of the user, the Windows user name, the name of the affiliated application, and the external user name.</span></span>  
  
3. <span data-ttu-id="958be-109">ISSOMapping.Create を呼び出して、マッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="958be-109">Create the mapping with a call to ISSOMapping.Create.</span></span>  
  
    <span data-ttu-id="958be-110">呼び出す`ISSOMapping.Create`をエンタープライズ シングル サインオン サーバーへのマッピングのローカル コピーを伝達します。</span><span class="sxs-lookup"><span data-stu-id="958be-110">Calling `ISSOMapping.Create` propagates the local copy of the mapping out to the Enterprise Single Sign-On server.</span></span>  
  
4. <span data-ttu-id="958be-111">呼び出して、マッピングの資格情報を設定`ISSOMapper.SetExternalCredentials`します。</span><span class="sxs-lookup"><span data-stu-id="958be-111">Set the credentials on the mapping with a call to `ISSOMapper.SetExternalCredentials`.</span></span>  
  
5. <span data-ttu-id="958be-112">呼び出して、マッピングを有効にする`ISSOMapping.Enable`します。</span><span class="sxs-lookup"><span data-stu-id="958be-112">Enable the mapping with a call to `ISSOMapping.Enable`.</span></span>  
  
   <span data-ttu-id="958be-113">次の例では、指定されたエンタープライズ シングル サインオン アプリケーションとユーザー間のマッピングを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="958be-113">The following example shows how to add mapping between a specified Enterprise Single Sign-On application and a user.</span></span>  
  
```  
public static bool AddMapping(string application, string user, string XU, string XP)  
{  
   try  
   {  
      // Set mapping.  
      ISSOMapper mapper=new ISSOMapper();  
      ISSOMapping mapping=new ISSOMapping();  
     string username=user.Substring(user.IndexOf('\\')+1);  
      string userdomain=user.Substring(0, user.IndexOf('\\'));  
      mapping.WindowsDomainName=userdomain;  
      mapping.WindowsUserName=username;  
      mapping.ApplicationName=application;  
      mapping.ExternalUserName=XU;  
      mapping.Create(0);  
      // Set credentials.  
      string[] credentials=new string[]{XP};  
      mapper.SetExternalCredentials(application, XU, ref credentials);  
      mapping.Enable(0);  
   }  
   catch  
   {  
      return false;  
   }  
   return true;  
      }  
```  
  
## <a name="see-also"></a><span data-ttu-id="958be-114">参照</span><span class="sxs-lookup"><span data-stu-id="958be-114">See Also</span></span>  
 [<span data-ttu-id="958be-115">Enterprise Single Sign-On によるプログラミング</span><span class="sxs-lookup"><span data-stu-id="958be-115">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)