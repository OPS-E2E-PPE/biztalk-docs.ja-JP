---
title: SSO サーバー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, tasks
- Master Secret server, SSO
- servers, SSO
- SSO, servers
- SSO, Master Secret server
ms.assetid: 40240d6b-b7d1-48fb-b750-be0e380d52e3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37f2f24911a0336a734125436d97dbce6f9e0b77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277618"
---
# <a name="sso-server"></a><span data-ttu-id="e1dc6-102">[SSO サーバー]</span><span class="sxs-lookup"><span data-stu-id="e1dc6-102">SSO Server</span></span>
<span data-ttu-id="e1dc6-103">エンタープライズ シングル サインオン (SSO) サーバーでは、次の作業を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e1dc6-103">The Enterprise Single Sign-On (SSO) server can perform any of the following tasks:</span></span>  
  
-   <span data-ttu-id="e1dc6-104">**マスター シークレット サーバーとして機能します。**</span><span class="sxs-lookup"><span data-stu-id="e1dc6-104">**Functions as the master secret server.**</span></span> <span data-ttu-id="e1dc6-105">マスタ シークレット サーバーには、SSO システム内のすべての資格情報を暗号化するために使用するマスタ シークレット (キー) のコピーが保存されます。</span><span class="sxs-lookup"><span data-stu-id="e1dc6-105">The master secret server holds a persisted copy of the master secret, or key, used to encrypt all the credentials in the SSO system.</span></span> <span data-ttu-id="e1dc6-106">マスタ シークレット サーバーを参照や管理のためのサーバーとして機能させることもできますが、セキュリティ上の理由から、マスタ シークレット サーバーとしてのみ使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e1dc6-106">Though the master secret server can act as a server for lookups and administration, it is recommended to use this server to act only as a master secret server for security reasons.</span></span> <span data-ttu-id="e1dc6-107">マスター シークレット サーバーを実行、関数の詳細については、次を参照してください。[マスター シークレット サーバー](../core/master-secret-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="e1dc6-107">For more information about the functions the master secret server performs, see [Master Secret Server](../core/master-secret-server.md).</span></span>  
  
-   <span data-ttu-id="e1dc6-108">**管理操作を実行します。**</span><span class="sxs-lookup"><span data-stu-id="e1dc6-108">**Performs administrative operations.**</span></span> <span data-ttu-id="e1dc6-109">SSO 管理者は、任意のシングル サインオン サーバーを使用して、関連アプリケーションの管理、ユーザー資格情報の設定、ユーザー マッピングの管理などの管理作業を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e1dc6-109">SSO administrators can use any of the Single Sign-On Servers to perform administrative tasks such as managing affiliate applications, setting user credentials, and managing user mappings.</span></span>  
  
-   <span data-ttu-id="e1dc6-110">**参照操作を実行します。**</span><span class="sxs-lookup"><span data-stu-id="e1dc6-110">**Performs lookup operations.**</span></span> <span data-ttu-id="e1dc6-111">SSO サーバーはランタイム コンポーネントを使用して、ユーザー資格情報を参照します。</span><span class="sxs-lookup"><span data-stu-id="e1dc6-111">The SSO server uses the runtime component to look up the user credentials.</span></span>  
  
-   <span data-ttu-id="e1dc6-112">**発行し、チケットを引き換えます。**</span><span class="sxs-lookup"><span data-stu-id="e1dc6-112">**Issues and Redeems Tickets.**</span></span> <span data-ttu-id="e1dc6-113">SSO サーバーは、SSO チケットの発行と引き換えを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="e1dc6-113">The SSO server also issues and redeems SSO tickets.</span></span>  
  
-   <span data-ttu-id="e1dc6-114">**パスワード同期します。**</span><span class="sxs-lookup"><span data-stu-id="e1dc6-114">**Password Synchronization.**</span></span> <span data-ttu-id="e1dc6-115">SSO サーバーでパスワード同期アダプタを作成して、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="e1dc6-115">You can create and manage password synchronization adapters on the SSO Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1dc6-116">参照</span><span class="sxs-lookup"><span data-stu-id="e1dc6-116">See Also</span></span>  
 <span data-ttu-id="e1dc6-117">[SSO の使用](../core/using-sso.md) </span><span class="sxs-lookup"><span data-stu-id="e1dc6-117">[Using SSO](../core/using-sso.md) </span></span>  
 [<span data-ttu-id="e1dc6-118">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="e1dc6-118">Installing SSO</span></span>](../core/installing-sso.md)