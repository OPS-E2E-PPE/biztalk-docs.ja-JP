---
title: メッセージのバージョン管理 Support1 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message versioning, support for
ms.assetid: 650b966e-9fa6-4af8-a061-7852a892717a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a2175ba0a3aafd052e6830439800569cf5f005f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-versioning-support"></a><span data-ttu-id="15cf8-102">メッセージ バージョン管理のサポート</span><span class="sxs-lookup"><span data-stu-id="15cf8-102">Message Versioning Support</span></span>
<span data-ttu-id="15cf8-103">[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]操作に対して表示されるメッセージ アクション、名前空間、およびノード Id でバージョン文字列の要素を含めることでバージョン管理をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="15cf8-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] supports versioning by including a version string component in the message actions, namespaces, and node IDs surfaced for operations.</span></span> <span data-ttu-id="15cf8-104">現在のバージョンは、http://Microsoft.LobServices.Sap/2007/03 です。</span><span class="sxs-lookup"><span data-stu-id="15cf8-104">The current version is http://Microsoft.LobServices.Sap/2007/03.</span></span> <span data-ttu-id="15cf8-105">つまりの"RFC_SAMPLE"という名前 RFC、アダプター、RFC 操作は、次の。</span><span class="sxs-lookup"><span data-stu-id="15cf8-105">This means that for an RFC named "RFC_SAMPLE", the RFC operation surfaced by the adapter has the following:</span></span>  
  
-   <span data-ttu-id="15cf8-106">ノード ID: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span><span class="sxs-lookup"><span data-stu-id="15cf8-106">Node ID: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span></span>  
  
-   <span data-ttu-id="15cf8-107">メッセージのアクション: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span><span class="sxs-lookup"><span data-stu-id="15cf8-107">Message action: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE</span></span>  
  
-   <span data-ttu-id="15cf8-108">Namespace: http://Microsoft.LobServices.Sap/2007/03/Rfc</span><span class="sxs-lookup"><span data-stu-id="15cf8-108">Namespace: http://Microsoft.LobServices.Sap/2007/03/Rfc</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15cf8-109">この機能は、アダプターの以前のバージョンとの下位互換性を提供しません。</span><span class="sxs-lookup"><span data-stu-id="15cf8-109">This feature does not provide backward compatibility with the earlier versions of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15cf8-110">参照</span><span class="sxs-lookup"><span data-stu-id="15cf8-110">See Also</span></span>  
 [<span data-ttu-id="15cf8-111">メッセージと BizTalk Adapter 用 mySAP Business Suite のメッセージ スキーマ</span><span class="sxs-lookup"><span data-stu-id="15cf8-111">Messages and Message Schemas for BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)