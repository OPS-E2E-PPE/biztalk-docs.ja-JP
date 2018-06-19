---
title: アダプターを使用して SAP システムへの接続 |Microsoft ドキュメント
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
ms.openlocfilehash: 75f8c4b8650b2c81b3b82bf520958646e20da380
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216898"
---
# <a name="connect-to-an-sap-system-using-the-adapter"></a><span data-ttu-id="7d713-102">アダプターを使用して SAP システムへの接続します。</span><span class="sxs-lookup"><span data-stu-id="7d713-102">Connect to an SAP system using the adapter</span></span>
<span data-ttu-id="7d713-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアント識別子 URI (Uniform Resource)、SAP システムに接続する接続と呼ばれる、接続文字列を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d713-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] requires adapter clients to provide a connection string, called the connection Uniform Resource Identifier (URI) to connect to the SAP system.</span></span> <span data-ttu-id="7d713-104">接続 URI のアダプターのクライアントは、外部システムに接続するための接続パラメーターを指定できます。接続 URI の詳細については、次を参照してください。 [SAP システムへの接続を作成する](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)です。</span><span class="sxs-lookup"><span data-stu-id="7d713-104">With a connection URI, adapter clients can specify connection parameters to connect to an external system.For more information about the connection URI, see [Create a connection to the SAP system](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md).</span></span>  
  
 <span data-ttu-id="7d713-105">SAP システムとの接続を確立するときに、セキュリティのガイドラインに従うことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7d713-105">Make sure you comply with the security guidelines when establishing a connection with an SAP system.</span></span> <span data-ttu-id="7d713-106">セキュリティに関するガイドラインの詳細については、次を参照してください。 [、SAP アプリケーションをセキュリティで保護された](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="7d713-106">For more information about security guidelines, see [Secure your SAP applications](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md).</span></span>
  
## <a name="how-many-connections-can-the-adapter-open-to-the-sap-system"></a><span data-ttu-id="7d713-107">接続の数が、アダプターの SAP システムを開くか。</span><span class="sxs-lookup"><span data-stu-id="7d713-107">How Many Connections Can the Adapter Open to the SAP System?</span></span>  
 <span data-ttu-id="7d713-108">既定では、SAP システムは、クライアントを開くには、SAP システムに 100 個の接続を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7d713-108">By default, the SAP system enables clients to open 100 connections to the SAP system.</span></span> <span data-ttu-id="7d713-109">ただし、接続の数の上限の引き上げを SAP システムを実行しているコンピューターで環境変数を設定できます。</span><span class="sxs-lookup"><span data-stu-id="7d713-109">However, you can set an environment variable on the computer running the SAP system to increase the limit on the number of connections.</span></span> <span data-ttu-id="7d713-110">詳細については、次を参照してください。 [SAP アダプターでの運用上の問題のトラブルシューティングを行う](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="7d713-110">For more information, see [Troubleshoot Operational Issues with the SAP adapter](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d713-111">参照</span><span class="sxs-lookup"><span data-stu-id="7d713-111">See Also</span></span>  
 [<span data-ttu-id="7d713-112">BizTalk Adapter 用 mySAP Business Suite のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="7d713-112">Architecture overview of the BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)