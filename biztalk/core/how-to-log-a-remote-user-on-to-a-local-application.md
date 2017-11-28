---
title: "リモート ユーザー、ローカルのアプリケーションにログオンする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 886ee7cb-e6ba-476a-bea9-4bb4c22bf94e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f638007c3c4eb1f85a5b5a701dd2b456c2d220d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-log-a-remote-user-on-to-a-local-application"></a><span data-ttu-id="3ae87-102">リモート ユーザー、ローカルのアプリケーションにログオンする方法</span><span class="sxs-lookup"><span data-stu-id="3ae87-102">How to Log a Remote User on to a Local Application</span></span>
<span data-ttu-id="3ae87-103">エンタープライズ シングル サインオン (ENTSSO) サービスの他の主要な機能は、ホスト側開始処理 (HIP) のサポートです。</span><span class="sxs-lookup"><span data-stu-id="3ae87-103">The other main feature of Enterprise Single Sign-On service (ENTSSO) is supporting a host-initiated process (HIP).</span></span> <span data-ttu-id="3ae87-104">リモート ユーザーがローカルの Windows リソースへのアクセスを試行するときに、ENTSSO は HIP と連携します。</span><span class="sxs-lookup"><span data-stu-id="3ae87-104">ENTSSO interacts with HIP when a remote user tries to access a local Windows resource.</span></span> <span data-ttu-id="3ae87-105">ENTSSO を使用して、ホスト ユーザーからの要求を受け取り、ローカル Windows アプリケーションへのアクセスを要求することができます。</span><span class="sxs-lookup"><span data-stu-id="3ae87-105">Using ENTSSO, you can receive the request from the host user and request access to the local Windows application.</span></span>  
  
## <a name="log-a-remote-user-on-to-a-local-windows-application"></a><span data-ttu-id="3ae87-106">リモート ユーザーによるローカル Windows アプリケーションにログオン</span><span class="sxs-lookup"><span data-stu-id="3ae87-106">Log a remote user on to a local Windows application</span></span>  
  
1.  <span data-ttu-id="3ae87-107">リモート ユーザーからの要求を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3ae87-107">Receive the request from the remote user.</span></span>  
  
     <span data-ttu-id="3ae87-108">リモート ユーザーから要求を受け取る方法は、適切に決定してください。</span><span class="sxs-lookup"><span data-stu-id="3ae87-108">It is your responsibility to determine how to retrieve a request from the remote user.</span></span>  
  
2.  <span data-ttu-id="3ae87-109">`ISSOLookup2.LogonExternalUser` を使用して、特定の関連アプリケーションに対するリモート ユーザーのアクセス許可を要求します。</span><span class="sxs-lookup"><span data-stu-id="3ae87-109">Request that the remote user be given access to the specified affiliate application, using `ISSOLookup2.LogonExternalUser`.</span></span>  
  
     <span data-ttu-id="3ae87-110">`LogonExternalUser` は、外部ユーザーがアクセスするアプリケーションの名前、外部ユーザー名、外部ユーザーに関連する資格情報、および関連フラグを渡します。</span><span class="sxs-lookup"><span data-stu-id="3ae87-110">`LogonExternalUser` passes in the name of the application the external user wishes to access, the name of the external user, the associated credentials for the external user, and any relevant flags.</span></span> <span data-ttu-id="3ae87-111">成功すると、`LogonExternalUser` は、Windows のアクセス トークンにハンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="3ae87-111">If successful, `LogonExternalUser` returns a handle to a Windows access token.</span></span>  
  
     <span data-ttu-id="3ae87-112">リモート ユーザーをシングル サインオン データベースで識別し、そのユーザーの資格情報をデータベースに格納し、関連アプリケーションに関連付けておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ae87-112">The remote user must already be identified in the Single Sign-On database, have their credentials in the database, and be associated with an affiliate application.</span></span> <span data-ttu-id="3ae87-113">これを行わないと、`LogonExternalUser` はエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="3ae87-113">Otherwise, `LogonExternalUser` returns an error.</span></span> <span data-ttu-id="3ae87-114">パスワード同期を使用して、ユーザー名および資格情報を常に最新にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3ae87-114">You can keep the user names and credentials up to date using Password Sync.</span></span>  
  
     <span data-ttu-id="3ae87-115">さらに、プロトコル遷移を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ae87-115">In addition, you must have protocol transition enabled.</span></span>  
  
3.  <span data-ttu-id="3ae87-116">`LogonExternalUser` から返される Windows ハンドルを使用して、トークンが表すユーザーの権限を借用します。</span><span class="sxs-lookup"><span data-stu-id="3ae87-116">Use the Windows handle returned from `LogonExternalUser` to impersonate the user that the token represents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ae87-117">参照</span><span class="sxs-lookup"><span data-stu-id="3ae87-117">See Also</span></span>  
 <span data-ttu-id="3ae87-118">[ローカル ユーザー、Windows 以外のアプリケーションにログオンする方法](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md) </span><span class="sxs-lookup"><span data-stu-id="3ae87-118">[How to Log a Local User on to a Non-Windows Application](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md) </span></span>  
 <span data-ttu-id="3ae87-119">**ISSOLookup2.LogonExternalUser メソッド**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="3ae87-119">**ISSOLookup2.LogonExternalUser Method** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>