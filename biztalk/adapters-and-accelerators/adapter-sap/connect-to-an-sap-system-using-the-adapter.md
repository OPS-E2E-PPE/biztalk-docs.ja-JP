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
# <a name="connect-to-an-sap-system-using-the-adapter"></a>アダプターを使用して SAP システムへの接続します。
[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアント識別子 URI (Uniform Resource)、SAP システムに接続する接続と呼ばれる、接続文字列を指定する必要があります。 接続 URI のアダプターのクライアントは、外部システムに接続するための接続パラメーターを指定できます。接続 URI の詳細については、次を参照してください。 [SAP システムへの接続を作成する](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)です。  
  
 SAP システムとの接続を確立するときに、セキュリティのガイドラインに従うことを確認します。 セキュリティに関するガイドラインの詳細については、次を参照してください。 [、SAP アプリケーションをセキュリティで保護された](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)です。
  
## <a name="how-many-connections-can-the-adapter-open-to-the-sap-system"></a>接続の数が、アダプターの SAP システムを開くか。  
 既定では、SAP システムは、クライアントを開くには、SAP システムに 100 個の接続を使用できます。 ただし、接続の数の上限の引き上げを SAP システムを実行しているコンピューターで環境変数を設定できます。 詳細については、次を参照してください。 [SAP アダプターでの運用上の問題のトラブルシューティングを行う](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter 用 mySAP Business Suite のアーキテクチャの概要](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)