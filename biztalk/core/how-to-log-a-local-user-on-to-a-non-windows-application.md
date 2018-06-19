---
title: ローカル ユーザー、Windows 以外のアプリケーションにログオンする方法 |Microsoft ドキュメント
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
ms.openlocfilehash: c3c2e9ffaede20e29987938a436ad2a091920fce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253874"
---
# <a name="how-to-log-a-local-user-on-to-a-non-windows-application"></a><span data-ttu-id="762fb-102">ローカル ユーザー、Windows 以外のアプリケーションにログオンする方法</span><span class="sxs-lookup"><span data-stu-id="762fb-102">How to Log a Local User on to a Non-Windows Application</span></span>
<span data-ttu-id="762fb-103">関連アプリケーションでユーザーを設定すると、シングル サインオン (SSO) を使用して、現在のユーザーの外部ユーザー名および資格情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="762fb-103">After you set up your user with an affiliate application, you can use Single Sign-On (SSO) to access the external user name and credentials of the current user.</span></span> <span data-ttu-id="762fb-104">これらの資格情報を使用することにより、ホスト サーバーで実行されている関連アプリケーションにユーザーをログオンさせることができます。</span><span class="sxs-lookup"><span data-stu-id="762fb-104">Using these credentials, you can then log your user on to the affiliate application that is running on a host server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="762fb-105">アプリケーションが正しいセキュリティ コンテキストで SSO を呼び出せるようにするには、SSO に対する適切なセキュリティ プロトコルの設定に加えて、追加のセキュリティ設定が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="762fb-105">In addition to setting the appropriate security protocols for SSO, you might also need to set additional security to allow your application to call SSO in the correct security context.</span></span> <span data-ttu-id="762fb-106">アプリケーションが正しいセキュリティ コンテキストで SSO を呼び出せない場合、アプリケーションへのアクセスが SSO によって拒否されます。</span><span class="sxs-lookup"><span data-stu-id="762fb-106">If your application cannot call SSO in the correct security context, SSO will deny access to your application.</span></span>  
  
### <a name="to-set-the-security-context-for-an-sso-application"></a><span data-ttu-id="762fb-107">SSO アプリケーションのセキュリティ コンテキストを設定するには</span><span class="sxs-lookup"><span data-stu-id="762fb-107">To set the security context for an SSO application</span></span>  
  
1.  <span data-ttu-id="762fb-108">アプリケーションが正常に動作するために必要な資格情報を特定します。</span><span class="sxs-lookup"><span data-stu-id="762fb-108">Identify what credentials your application needs to run successfully.</span></span>  
  
     <span data-ttu-id="762fb-109">たとえば、Web サービスまたは IIS でホストされている .NET Framework リモート処理を使用するアプリケーションでは、SSO に適切な資格情報を渡すために、クライアントを偽装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="762fb-109">For example, an application that uses Web services or .NET Framework remoting hosted in IIS needs to impersonate the client in order to pass the appropriate credentials on to SSO.</span></span>  
  
2.  <span data-ttu-id="762fb-110">関連するセキュリティ設定 (仮想ディレクトリ、アプリケーション プール、web.config ファイルなどのセキュリティ設定) が、これらの資格情報をアプリケーションに提供するように設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="762fb-110">Confirm that the relevant security settings, such as those on virtual directories, application pools, and web.config files, are set to provide your application with those credentials.</span></span>  
  
     <span data-ttu-id="762fb-111">セキュリティ資格情報を設定する方法の詳細については、次を参照してください。[セキュリティで保護された ASP.NET アプリケーションの構築: 認証、承認、およびセキュリティ保護された通信](http://go.microsoft.com/fwlink/?LinkId=193906)です。</span><span class="sxs-lookup"><span data-stu-id="762fb-111">For more information about how to set security credentials, see [Building Secure ASP.NET Applications: Authentication, Authorization, and Secure Communication](http://go.microsoft.com/fwlink/?LinkId=193906).</span></span>  
  
     <span data-ttu-id="762fb-112">ASP.NET Web サービスの資格情報の詳細については、次を参照してください。 [HOW TO: 渡す現在の資格情報を ASP.NET Web サービス](http://go.microsoft.com/fwlink/?LinkId=193907)です。</span><span class="sxs-lookup"><span data-stu-id="762fb-112">For more information about passing credentials for an ASP.NET Web service, see [HOW TO: Pass Current Credentials to an ASP.NET Web Service](http://go.microsoft.com/fwlink/?LinkId=193907).</span></span>  
  
### <a name="to-log-a-local-user-on-to-a-host-application"></a><span data-ttu-id="762fb-113">ローカル ユーザーがホスト アプリケーションにログオンするには</span><span class="sxs-lookup"><span data-stu-id="762fb-113">To log a local user on to a host application</span></span>  
  
1.  <span data-ttu-id="762fb-114">ホスト サーバーで実行されているアプリケーションに現在のユーザーをログオンするための要求を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="762fb-114">Receive the request to log the current user on to an application running on the host server.</span></span>  
  
     <span data-ttu-id="762fb-115">ホスト アプリケーションへのログオンをユーザーが要求する方法は、適切に決定してください。</span><span class="sxs-lookup"><span data-stu-id="762fb-115">It is your responsibility to determine how the current user requests to be logged on to a host application.</span></span>  
  
2.  <span data-ttu-id="762fb-116">`ISSOLookup1.GetCredentials` または `ISSOLookup2.GetCredentials` を使用している現在のユーザーの資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="762fb-116">Retrieve the credentials for the current user who is using `ISSOLookup1.GetCredentials` or `ISSOLookup2.GetCredentials`.</span></span>  
  
     <span data-ttu-id="762fb-117">関連フラグと共に、ホスト アプリケーションの名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="762fb-117">You must supply the name of the host application together with any relevant flags.</span></span> <span data-ttu-id="762fb-118">`GetCredentials`関連付けられたユーザー名とホスト アプリケーションの資格情報を返します。</span><span class="sxs-lookup"><span data-stu-id="762fb-118">`GetCredentials` returns the associated user name and credentials for the host application.</span></span>  
  
     <span data-ttu-id="762fb-119">`ISSOLookup1` または `ISSOLookup2` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="762fb-119">Note that you can use either `ISSOLookup1` or `ISSOLookup2`.</span></span> <span data-ttu-id="762fb-120">この 2 つの違いは、`ISSOLookup2` には、リモート ユーザーによるローカル Windows アプリケーションへのログオン方法も含まれている点です。</span><span class="sxs-lookup"><span data-stu-id="762fb-120">The only difference is that `ISSOLookup2` also has a method for logging a remote user on to a local windows application.</span></span>  
  
3.  <span data-ttu-id="762fb-121">外部ユーザー名と資格情報を使用して、ホスト アプリケーションにログオンします。</span><span class="sxs-lookup"><span data-stu-id="762fb-121">Use the external user name and credentials to log on to the host application.</span></span>  
  
     <span data-ttu-id="762fb-122">資格情報を使用してホスト アプリケーションにログオンする方法は、適切に決定してください。</span><span class="sxs-lookup"><span data-stu-id="762fb-122">It is your responsibility to determine how to use the credentials to log on to the host application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="762fb-123">参照</span><span class="sxs-lookup"><span data-stu-id="762fb-123">See Also</span></span>  
 [<span data-ttu-id="762fb-124">リモート ユーザー、ローカルのアプリケーションにログオンする方法</span><span class="sxs-lookup"><span data-stu-id="762fb-124">How to Log a Remote User on to a Local Application</span></span>](../core/how-to-log-a-remote-user-on-to-a-local-application.md)