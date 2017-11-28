---
title: "シングル サインオン資格情報をマップする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e847bde9-7a4c-4b81-8ad6-6a7cf23d19a1
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a2717a990cf6ac2bac92067354afd42931c9a75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-map-single-sign-on-credentials"></a><span data-ttu-id="bafe7-102">シングル サインオン資格情報をマップする方法</span><span class="sxs-lookup"><span data-stu-id="bafe7-102">How to Map Single Sign-On Credentials</span></span>
<span data-ttu-id="bafe7-103">エンタープライズ シングル サインオン データベース内に関連アプリケーションがあれば、ユーザーの資格情報をそのアプリケーションにマップできます。</span><span class="sxs-lookup"><span data-stu-id="bafe7-103">When you know that you have affiliated applications in your Enterprise Single Sign-On database, you can map the credentials for a user to that application.</span></span> <span data-ttu-id="bafe7-104">現在のユーザーの資格情報を関連アプリケーションにマップする場合、`ISSOMapper` インターフェイスおよび `ISSOMapping` インターフェイスを組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bafe7-104">Mapping the credentials of the current user to an affiliated application requires that you use a combination of the `ISSOMapper` and `ISSOMapping` interfaces.</span></span>  
  
### <a name="to-map-between-an-affiliated-application-and-user-credentials"></a><span data-ttu-id="bafe7-105">関連アプリケーションとユーザーの資格情報をマップするには</span><span class="sxs-lookup"><span data-stu-id="bafe7-105">To map between an affiliated application and user credentials</span></span>  
  
1.  <span data-ttu-id="bafe7-106">`ISSOMapper` および `ISSOMapping` の新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="bafe7-106">Create new instances of `ISSOMapper` and `ISSOMapping`.</span></span>  
  
2.  <span data-ttu-id="bafe7-107">`ISSOMapping` プロパティを適切な値に設定します。</span><span class="sxs-lookup"><span data-stu-id="bafe7-107">Set the `ISSOMapping` properties to the relevant values.</span></span>  
  
     <span data-ttu-id="bafe7-108">`ISSOMapping` に指定できるプロパティは、ユーザーの Microsoft Windows ドメイン名、Windows ユーザー名、関連アプリケーションの名前、または外部ユーザー名です。</span><span class="sxs-lookup"><span data-stu-id="bafe7-108">The relevant properties for `ISSOMapping` are the Microsoft Windows domain name of the user, the Windows user name, the name of the affiliated application, and the external user name.</span></span>  
  
3.  <span data-ttu-id="bafe7-109">ISSOMapping.Create を呼び出して、マッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="bafe7-109">Create the mapping with a call to ISSOMapping.Create.</span></span>  
  
     <span data-ttu-id="bafe7-110">`ISSOMapping.Create` を呼び出すと、エンタープライズ シングル サインオン サーバーにマップするローカル コピーに反映されます。</span><span class="sxs-lookup"><span data-stu-id="bafe7-110">Calling `ISSOMapping.Create` propagates the local copy of the mapping out to the Enterprise Single Sign-On server.</span></span>  
  
4.  <span data-ttu-id="bafe7-111">`ISSOMapper.SetExternalCredentials` を呼び出して、マッピングの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="bafe7-111">Set the credentials on the mapping with a call to `ISSOMapper.SetExternalCredentials`.</span></span>  
  
5.  <span data-ttu-id="bafe7-112">`ISSOMapping.Enable` を呼び出して、マッピングを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bafe7-112">Enable the mapping with a call to `ISSOMapping.Enable`.</span></span>  
  
 <span data-ttu-id="bafe7-113">次の例は、指定されたエンタープライズ シングル サインオン アプリケーションとユーザーのマッピングを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bafe7-113">The following example shows how to add mapping between a specified Enterprise Single Sign-On application and a user.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bafe7-114">参照</span><span class="sxs-lookup"><span data-stu-id="bafe7-114">See Also</span></span>  
 [<span data-ttu-id="bafe7-115">エンタープライズ シングル サインオンを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="bafe7-115">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)