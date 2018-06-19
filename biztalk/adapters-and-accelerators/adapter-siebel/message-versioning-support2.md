---
title: メッセージのバージョン管理 Support2 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message versioning, support for
ms.assetid: 5b7b9202-9f45-450e-918f-b26a03711aab
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04514a9c55fa29a930b6ba7467177d6a754ff3db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221858"
---
# <a name="message-versioning-support"></a><span data-ttu-id="5737b-102">メッセージ バージョン管理のサポート</span><span class="sxs-lookup"><span data-stu-id="5737b-102">Message Versioning Support</span></span>
<span data-ttu-id="5737b-103">[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]操作に対して表示されるメッセージ アクション、名前空間、およびノード Id でバージョン文字列の要素を含めることでバージョン管理をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5737b-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] supports versioning by including a version string component in the message actions, namespaces, and node IDs surfaced for operations.</span></span> <span data-ttu-id="5737b-104">現在のバージョンは、http://Microsoft.LobServices.Siebel/2007/03 です。</span><span class="sxs-lookup"><span data-stu-id="5737b-104">The current version is http://Microsoft.LobServices.Siebel/2007/03.</span></span> <span data-ttu-id="5737b-105">つまり、Siebel リポジトリ内のアカウント ビジネス オブジェクトの挿入操作の場合、アダプターによって公開される挿入操作は、次。</span><span class="sxs-lookup"><span data-stu-id="5737b-105">This means that for an Insert operation on an Account business object in the Siebel repository, the Insert operation surfaced by the adapter has the following:</span></span>  
  
-   <span data-ttu-id="5737b-106">ノード ID: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span><span class="sxs-lookup"><span data-stu-id="5737b-106">Node ID: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span></span>  
  
-   <span data-ttu-id="5737b-107">メッセージのアクション: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span><span class="sxs-lookup"><span data-stu-id="5737b-107">Message action: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert</span></span>  
  
-   <span data-ttu-id="5737b-108">Namespace: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation</span><span class="sxs-lookup"><span data-stu-id="5737b-108">Namespace: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5737b-109">この機能は、アダプターの以前のバージョンとの下位互換性を提供しません。</span><span class="sxs-lookup"><span data-stu-id="5737b-109">This feature does not provide backward compatibility with the earlier versions of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5737b-110">参照</span><span class="sxs-lookup"><span data-stu-id="5737b-110">See Also</span></span>  
 [<span data-ttu-id="5737b-111">メッセージと BizTalk Adapter for Siebel eBusiness Applications のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="5737b-111">Messages and Message Schemas for BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)