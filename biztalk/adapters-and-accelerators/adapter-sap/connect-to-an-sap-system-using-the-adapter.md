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
# <a name="connect-to-an-sap-system-using-the-adapter"></a>アダプターを使用して SAP システムへの接続します。
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアント接続、SAP システムへの接続に統一リソース識別子 (URI) と呼ばれる接続文字列を指定する必要があります。 接続 URI では、アダプター クライアントは、外部システムに接続する接続パラメーターを指定できます。接続 URI の詳細については、次を参照してください。 [SAP システムへの接続を作成する](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)します。  
  
 SAP システムとの接続を確立するときに、セキュリティのガイドラインに従うことを確認します。 セキュリティのガイドラインの詳細については、次を参照してください。 [SAP アプリケーションのセキュリティ保護](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)します。
  
## <a name="how-many-connections-can-the-adapter-open-to-the-sap-system"></a>接続の数は、アダプター、SAP システムを開くか?  
 既定では、SAP システムは、SAP システムに 100 個の接続を開くクライアントを使用できます。 ただし、接続の数に上限を引き上げて、SAP システムを実行するコンピューターで環境変数を設定できます。 詳細については、次を参照してください。 [SAP アダプターを使用した運用上の問題のトラブルシューティングを行う](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for mySAP Business Suite のアーキテクチャの概要](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)