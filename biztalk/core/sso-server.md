---
title: SSO サーバー |Microsoft Docs
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
ms.openlocfilehash: 7a17d3ad69ab18e9d1916f5a7cf2907021d7d54c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398985"
---
# <a name="sso-server"></a><span data-ttu-id="06785-102">SSO サーバー</span><span class="sxs-lookup"><span data-stu-id="06785-102">SSO Server</span></span>
<span data-ttu-id="06785-103">エンタープライズ シングル サインオン (SSO) サーバーは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="06785-103">The Enterprise Single Sign-On (SSO) server can perform any of the following tasks:</span></span>  
  
-   <span data-ttu-id="06785-104">**マスター シークレット サーバーとして機能します。**</span><span class="sxs-lookup"><span data-stu-id="06785-104">**Functions as the master secret server.**</span></span> <span data-ttu-id="06785-105">マスター シークレット サーバーは、マスター シークレットの永続化されたコピーを保持またはキー、SSO システムですべての資格情報を暗号化するために使用します。</span><span class="sxs-lookup"><span data-stu-id="06785-105">The master secret server holds a persisted copy of the master secret, or key, used to encrypt all the credentials in the SSO system.</span></span> <span data-ttu-id="06785-106">ただし、マスター シークレット サーバーでの検索および管理サーバーとして機能できますは、このサーバーを使用して、セキュリティ上の理由からマスター シークレット サーバーとしてのみ機能することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="06785-106">Though the master secret server can act as a server for lookups and administration, it is recommended to use this server to act only as a master secret server for security reasons.</span></span> <span data-ttu-id="06785-107">マスター シークレット サーバーを実行、関数の詳細については、次を参照してください。[マスター シークレット サーバー](../core/master-secret-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="06785-107">For more information about the functions the master secret server performs, see [Master Secret Server](../core/master-secret-server.md).</span></span>  
  
-   <span data-ttu-id="06785-108">**管理操作を実行します。**</span><span class="sxs-lookup"><span data-stu-id="06785-108">**Performs administrative operations.**</span></span> <span data-ttu-id="06785-109">SSO 管理者は関連のアプリケーションの管理などの管理タスクを実行するシングル サインオン サーバーのいずれかを使用できるユーザー資格情報を設定してユーザー マッピングを管理します。</span><span class="sxs-lookup"><span data-stu-id="06785-109">SSO administrators can use any of the Single Sign-On Servers to perform administrative tasks such as managing affiliate applications, setting user credentials, and managing user mappings.</span></span>  
  
-   <span data-ttu-id="06785-110">**参照操作を実行します。**</span><span class="sxs-lookup"><span data-stu-id="06785-110">**Performs lookup operations.**</span></span> <span data-ttu-id="06785-111">SSO サーバーは、ユーザーの資格情報を検索するランタイム コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="06785-111">The SSO server uses the runtime component to look up the user credentials.</span></span>  
  
-   <span data-ttu-id="06785-112">**問題およびチケットの引き換えを行います。**</span><span class="sxs-lookup"><span data-stu-id="06785-112">**Issues and Redeems Tickets.**</span></span> <span data-ttu-id="06785-113">SSO サーバーの発行もと SSO チケットの引き換え。</span><span class="sxs-lookup"><span data-stu-id="06785-113">The SSO server also issues and redeems SSO tickets.</span></span>  
  
-   <span data-ttu-id="06785-114">**パスワード同期します。**</span><span class="sxs-lookup"><span data-stu-id="06785-114">**Password Synchronization.**</span></span> <span data-ttu-id="06785-115">作成し、SSO サーバーでパスワード同期アダプタを管理します。</span><span class="sxs-lookup"><span data-stu-id="06785-115">You can create and manage password synchronization adapters on the SSO Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06785-116">参照</span><span class="sxs-lookup"><span data-stu-id="06785-116">See Also</span></span>  
 <span data-ttu-id="06785-117">[SSO を使用してください。](../core/using-sso.md) </span><span class="sxs-lookup"><span data-stu-id="06785-117">[Using SSO](../core/using-sso.md) </span></span>  
 [<span data-ttu-id="06785-118">SSO のインストール</span><span class="sxs-lookup"><span data-stu-id="06785-118">Installing SSO</span></span>](../core/installing-sso.md)