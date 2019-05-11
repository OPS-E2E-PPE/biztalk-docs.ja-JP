---
title: リモート ユーザー アプリケーションをローカルにログオンする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 886ee7cb-e6ba-476a-bea9-4bb4c22bf94e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fa3e3251961cb4d58d07026948a09fee94c2942
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336812"
---
# <a name="how-to-log-a-remote-user-on-to-a-local-application"></a><span data-ttu-id="18ccb-102">リモート ユーザー アプリケーションをローカルにログオンする方法</span><span class="sxs-lookup"><span data-stu-id="18ccb-102">How to Log a Remote User on to a Local Application</span></span>
<span data-ttu-id="18ccb-103">エンタープライズ シングル サインオン サービス (ENTSSO) の他の主な機能がサポートしているホスト側開始処理 (HIP)。</span><span class="sxs-lookup"><span data-stu-id="18ccb-103">The other main feature of Enterprise Single Sign-On service (ENTSSO) is supporting a host-initiated process (HIP).</span></span> <span data-ttu-id="18ccb-104">ENTSSO は HIP と連携リモート ユーザーはローカルの Windows リソースにアクセスしようとしています。</span><span class="sxs-lookup"><span data-stu-id="18ccb-104">ENTSSO interacts with HIP when a remote user tries to access a local Windows resource.</span></span> <span data-ttu-id="18ccb-105">ENTSSO を使用してから受信できる要求ホストのユーザーと要求のアクセスをローカルの Windows アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="18ccb-105">Using ENTSSO, you can receive the request from the host user and request access to the local Windows application.</span></span>  
  
## <a name="log-a-remote-user-on-to-a-local-windows-application"></a><span data-ttu-id="18ccb-106">リモート ユーザーをローカルの Windows アプリケーションにログオン</span><span class="sxs-lookup"><span data-stu-id="18ccb-106">Log a remote user on to a local Windows application</span></span>  
  
1.  <span data-ttu-id="18ccb-107">リモート ユーザーから要求を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="18ccb-107">Receive the request from the remote user.</span></span>  
  
     <span data-ttu-id="18ccb-108">適切に、リモート ユーザーから要求を取得する方法を決定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="18ccb-108">It is your responsibility to determine how to retrieve a request from the remote user.</span></span>  
  
2.  <span data-ttu-id="18ccb-109">リモート ユーザーが、指定された関連アプリケーションへのアクセス権を付与することを要求を使用して`ISSOLookup2.LogonExternalUser`します。</span><span class="sxs-lookup"><span data-stu-id="18ccb-109">Request that the remote user be given access to the specified affiliate application, using `ISSOLookup2.LogonExternalUser`.</span></span>  
  
     <span data-ttu-id="18ccb-110">`LogonExternalUser` 外部ユーザーをアプリケーションの名前のパスにアクセスする外部のユーザーと関連するフラグのいずれかの外部ユーザーは、関連付けられている資格情報の名前に希望しています。</span><span class="sxs-lookup"><span data-stu-id="18ccb-110">`LogonExternalUser` passes in the name of the application the external user wishes to access, the name of the external user, the associated credentials for the external user, and any relevant flags.</span></span> <span data-ttu-id="18ccb-111">成功した場合、 `LogonExternalUser` Windows アクセス トークンへのハンドルを返します。</span><span class="sxs-lookup"><span data-stu-id="18ccb-111">If successful, `LogonExternalUser` returns a handle to a Windows access token.</span></span>  
  
     <span data-ttu-id="18ccb-112">リモート ユーザーが既にありますでシングル サインオン データベースで識別される、データベース内の資格情報があるし、関連アプリケーションに関連付けます。</span><span class="sxs-lookup"><span data-stu-id="18ccb-112">The remote user must already be identified in the Single Sign-On database, have their credentials in the database, and be associated with an affiliate application.</span></span> <span data-ttu-id="18ccb-113">それ以外の場合、`LogonExternalUser`エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="18ccb-113">Otherwise, `LogonExternalUser` returns an error.</span></span> <span data-ttu-id="18ccb-114">ユーザー名とパスワード同期を使用して資格情報を保持することができます。</span><span class="sxs-lookup"><span data-stu-id="18ccb-114">You can keep the user names and credentials up to date using Password Sync.</span></span>  
  
     <span data-ttu-id="18ccb-115">さらに、プロトコル遷移を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="18ccb-115">In addition, you must have protocol transition enabled.</span></span>  
  
3.  <span data-ttu-id="18ccb-116">返される Windows ハンドルを使用して`LogonExternalUser`トークンを表すユーザーを偽装します。</span><span class="sxs-lookup"><span data-stu-id="18ccb-116">Use the Windows handle returned from `LogonExternalUser` to impersonate the user that the token represents.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18ccb-117">参照</span><span class="sxs-lookup"><span data-stu-id="18ccb-117">See Also</span></span>  
 <span data-ttu-id="18ccb-118">[ローカル ユーザー非 Windows アプリケーションにログオンする方法](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md) </span><span class="sxs-lookup"><span data-stu-id="18ccb-118">[How to Log a Local User on to a Non-Windows Application](../core/how-to-log-a-local-user-on-to-a-non-windows-application.md) </span></span>  
 <span data-ttu-id="18ccb-119">**ISSOLookup2.LogonExternalUser メソッド** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="18ccb-119">**ISSOLookup2.LogonExternalUser Method** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>