---
title: アダプターを使用して SAP システムへの接続 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI
- adapters, connecting to an SAP system
- connection string
ms.assetid: d506a948-5f4a-420b-a404-508824683099
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b8c470d294124826d79903fcdf6eef54303f646
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373681"
---
# <a name="connect-to-an-sap-system-using-the-adapter"></a><span data-ttu-id="9a2ae-102">アダプターを使用して SAP システムへの接続します。</span><span class="sxs-lookup"><span data-stu-id="9a2ae-102">Connect to an SAP system using the adapter</span></span>
<span data-ttu-id="9a2ae-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアント接続、SAP システムへの接続に統一リソース識別子 (URI) と呼ばれる接続文字列を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a2ae-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] requires adapter clients to provide a connection string, called the connection Uniform Resource Identifier (URI) to connect to the SAP system.</span></span> <span data-ttu-id="9a2ae-104">接続 URI では、アダプター クライアントは、外部システムに接続する接続パラメーターを指定できます。接続 URI の詳細については、次を参照してください。 [SAP システムへの接続を作成する](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="9a2ae-104">With a connection URI, adapter clients can specify connection parameters to connect to an external system.For more information about the connection URI, see [Create a connection to the SAP system](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).</span></span>  
  
 <span data-ttu-id="9a2ae-105">SAP システムとの接続を確立するときに、セキュリティのガイドラインに従うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a2ae-105">Make sure you comply with the security guidelines when establishing a connection with an SAP system.</span></span> <span data-ttu-id="9a2ae-106">セキュリティのガイドラインの詳細については、次を参照してください。 [SAP アプリケーションのセキュリティ保護](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="9a2ae-106">For more information about security guidelines, see [Secure your SAP applications](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md).</span></span>
  
## <a name="how-many-connections-can-the-adapter-open-to-the-sap-system"></a><span data-ttu-id="9a2ae-107">接続の数は、アダプター、SAP システムを開くか?</span><span class="sxs-lookup"><span data-stu-id="9a2ae-107">How Many Connections Can the Adapter Open to the SAP System?</span></span>  
 <span data-ttu-id="9a2ae-108">既定では、SAP システムは、SAP システムに 100 個の接続を開くクライアントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9a2ae-108">By default, the SAP system enables clients to open 100 connections to the SAP system.</span></span> <span data-ttu-id="9a2ae-109">ただし、接続の数に上限を引き上げて、SAP システムを実行するコンピューターで環境変数を設定できます。</span><span class="sxs-lookup"><span data-stu-id="9a2ae-109">However, you can set an environment variable on the computer running the SAP system to increase the limit on the number of connections.</span></span> <span data-ttu-id="9a2ae-110">詳細については、次を参照してください。 [SAP アダプターを使用した運用上の問題のトラブルシューティングを行う](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="9a2ae-110">For more information, see [Troubleshoot Operational Issues with the SAP adapter](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a2ae-111">参照</span><span class="sxs-lookup"><span data-stu-id="9a2ae-111">See Also</span></span>  
 [<span data-ttu-id="9a2ae-112">BizTalk Adapter for mySAP Business Suite のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="9a2ae-112">Architecture overview of the BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)