---
title: ローカル ユーザー非 Windows アプリケーションにログオンする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b55957f4-22c4-48b5-827a-ab41d8f846ac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3a403ff5e5d31b807e443377b0ca7954dd74efb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384751"
---
# <a name="how-to-log-a-local-user-on-to-a-non-windows-application"></a><span data-ttu-id="dc142-102">ローカル ユーザー非 Windows アプリケーションにログオンする方法</span><span class="sxs-lookup"><span data-stu-id="dc142-102">How to Log a Local User on to a Non-Windows Application</span></span>
<span data-ttu-id="dc142-103">関連アプリケーションでユーザーを設定した後は、外部ユーザー名と、現在のユーザーの資格情報にアクセスするのにシングル サインオン (SSO) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="dc142-103">After you set up your user with an affiliate application, you can use Single Sign-On (SSO) to access the external user name and credentials of the current user.</span></span> <span data-ttu-id="dc142-104">これらの資格情報を使用して、ユーザーは、ホスト サーバーで実行されている関連アプリケーションにログオンし、ログオンできます。</span><span class="sxs-lookup"><span data-stu-id="dc142-104">Using these credentials, you can then log your user on to the affiliate application that is running on a host server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc142-105">Sso には、適切なセキュリティ プロトコルを設定するだけでなく、適切なセキュリティ コンテキストで SSO を呼び出すようにアプリケーションを許可する追加のセキュリティを設定する可能性がありますも必要です。</span><span class="sxs-lookup"><span data-stu-id="dc142-105">In addition to setting the appropriate security protocols for SSO, you might also need to set additional security to allow your application to call SSO in the correct security context.</span></span> <span data-ttu-id="dc142-106">アプリケーションでは、適切なセキュリティ コンテキストで SSO を呼び出すことはできません、SSO により、アプリケーションへのアクセスが拒否されます。</span><span class="sxs-lookup"><span data-stu-id="dc142-106">If your application cannot call SSO in the correct security context, SSO will deny access to your application.</span></span>  
  
### <a name="to-set-the-security-context-for-an-sso-application"></a><span data-ttu-id="dc142-107">SSO アプリケーションのセキュリティ コンテキストを設定するには</span><span class="sxs-lookup"><span data-stu-id="dc142-107">To set the security context for an SSO application</span></span>  
  
1.  <span data-ttu-id="dc142-108">資格情報を正常に実行するアプリケーションのニーズを特定します。</span><span class="sxs-lookup"><span data-stu-id="dc142-108">Identify what credentials your application needs to run successfully.</span></span>  
  
     <span data-ttu-id="dc142-109">たとえば、Web サービスまたは IIS でホストされている .NET Framework リモート処理を使用するアプリケーションは、SSO に適切な資格情報を渡すためにクライアントを偽装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc142-109">For example, an application that uses Web services or .NET Framework remoting hosted in IIS needs to impersonate the client in order to pass the appropriate credentials on to SSO.</span></span>  
  
2.  <span data-ttu-id="dc142-110">これらの資格情報を使用してアプリケーションを提供する仮想ディレクトリ、アプリケーション プール、および web.config ファイルであるよう、関連するセキュリティ設定を設定することを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc142-110">Confirm that the relevant security settings, such as those on virtual directories, application pools, and web.config files, are set to provide your application with those credentials.</span></span>  
  
     <span data-ttu-id="dc142-111">セキュリティ資格情報を設定する方法の詳細については、次を参照してください[Building Secure ASP.NET Applications:。認証、承認、およびセキュリティで保護された通信](http://go.microsoft.com/fwlink/?LinkId=193906)します。</span><span class="sxs-lookup"><span data-stu-id="dc142-111">For more information about how to set security credentials, see [Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](http://go.microsoft.com/fwlink/?LinkId=193906).</span></span>  
  
     <span data-ttu-id="dc142-112">ASP.NET Web サービスの資格情報の詳細については、次を参照してください[HOW TO:。ASP.NET Web サービスに現在の資格情報を渡す](http://go.microsoft.com/fwlink/?LinkId=193907)します。</span><span class="sxs-lookup"><span data-stu-id="dc142-112">For more information about passing credentials for an ASP.NET Web service, see [HOW TO: Pass Current Credentials to an ASP.NET Web Service](http://go.microsoft.com/fwlink/?LinkId=193907).</span></span>  
  
### <a name="to-log-a-local-user-on-to-a-host-application"></a><span data-ttu-id="dc142-113">ローカル ユーザー、ホスト アプリケーションにログオンする</span><span class="sxs-lookup"><span data-stu-id="dc142-113">To log a local user on to a host application</span></span>  
  
1.  <span data-ttu-id="dc142-114">ホスト サーバーで実行されているアプリケーションは、現在のユーザーのログイン要求を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="dc142-114">Receive the request to log the current user on to an application running on the host server.</span></span>  
  
     <span data-ttu-id="dc142-115">ホスト アプリケーションにログオンする、現在のユーザーの要求を特定するユーザーの責任になります。</span><span class="sxs-lookup"><span data-stu-id="dc142-115">It is your responsibility to determine how the current user requests to be logged on to a host application.</span></span>  
  
2.  <span data-ttu-id="dc142-116">使用している現在のユーザーの資格情報を取得`ISSOLookup1.GetCredentials`または`ISSOLookup2.GetCredentials`します。</span><span class="sxs-lookup"><span data-stu-id="dc142-116">Retrieve the credentials for the current user who is using `ISSOLookup1.GetCredentials` or `ISSOLookup2.GetCredentials`.</span></span>  
  
     <span data-ttu-id="dc142-117">関連フラグと共に、ホスト アプリケーションの名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc142-117">You must supply the name of the host application together with any relevant flags.</span></span> <span data-ttu-id="dc142-118">`GetCredentials` 関連付けられたユーザー名とホスト アプリケーションの資格情報を返します。</span><span class="sxs-lookup"><span data-stu-id="dc142-118">`GetCredentials` returns the associated user name and credentials for the host application.</span></span>  
  
     <span data-ttu-id="dc142-119">使用しますか`ISSOLookup1`または`ISSOLookup2`します。</span><span class="sxs-lookup"><span data-stu-id="dc142-119">Note that you can use either `ISSOLookup1` or `ISSOLookup2`.</span></span> <span data-ttu-id="dc142-120">唯一の違いは`ISSOLookup2`ローカル windows アプリケーションへのリモート ユーザーがログインするためのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="dc142-120">The only difference is that `ISSOLookup2` also has a method for logging a remote user on to a local windows application.</span></span>  
  
3.  <span data-ttu-id="dc142-121">ホスト アプリケーションにログオンするには、外部ユーザー名と資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc142-121">Use the external user name and credentials to log on to the host application.</span></span>  
  
     <span data-ttu-id="dc142-122">適切に資格情報を使用して、ホスト アプリケーションにログオンする方法を決定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dc142-122">It is your responsibility to determine how to use the credentials to log on to the host application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc142-123">参照</span><span class="sxs-lookup"><span data-stu-id="dc142-123">See Also</span></span>  
 [<span data-ttu-id="dc142-124">リモート ユーザー アプリケーションをローカルにログオンする方法</span><span class="sxs-lookup"><span data-stu-id="dc142-124">How to Log a Remote User on to a Local Application</span></span>](../core/how-to-log-a-remote-user-on-to-a-local-application.md)