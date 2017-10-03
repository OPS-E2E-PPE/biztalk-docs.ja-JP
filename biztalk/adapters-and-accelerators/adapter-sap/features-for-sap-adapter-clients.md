---
title: "SAP アダプターのクライアントの機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dynamic ports
- adapters, features
- XML data streaming
- performance counters
- adapters, support for dynamic ports in BizTalk Server
- adapters, support for message versioning
- adapters, support for XML data streaming
- adapters, support for performance counters
- adapters, support for configuring adapters using binding properties
ms.assetid: 9003c2c1-931d-405e-9a58-660032195af7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6516ff99f599d02cdf27aa7c0c07752747749021
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="features-for-sap-adapter-clients"></a>SAP アダプターのクライアントの機能
トピックで説明されている機能だけでなく[BizTalk adapter 用 mySAP Business Suite のアーキテクチャの概要](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアント用の便利な次の機能も提供します。  
  
-   **バインドのプロパティを使用してアダプターを構成するためのサポート**です。 アダプターのクライアントを構成することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を特定のバインディング プロパティを指定します。 クライアントが値を指定して、アダプターの接続プール内で接続の最大数を指定するアダプターを構成するなど、 **MaxConnectionsPerSystem**プロパティをバインドします。 詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)です。  
  
-   **BizTalk Server での動的ポートのサポート**です。 BizTalk を通じて[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]からのメッセージの動的なルーティングできるようにする動的なポートをサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキスト プロパティに基づきます。 詳細については、次を参照してください。[動的ポートを構成する](../../adapters-and-accelerators/adapter-sap/configure-dynamic-ports-in-the-sap-adapter.md)です。
  
-   **メッセージのバージョン管理のサポート**です。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージのさまざまなメッセージ スキーマの将来のリリースでのサポートを有効にバージョン管理をサポートしています、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。 詳細については、次を参照してください。[メッセージ バージョン管理サポート](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md)です。  
  
    > [!NOTE]
    >  この機能は、アダプターの以前のバージョンとの下位互換性を提供しません。  
  
-   **パフォーマンス カウンターのサポート**です。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアントで使用する WCF ベースのパフォーマンス カウンターをサポートしています。 パフォーマンス カウンターの詳細については、次を参照してください。 [SAP アダプターのパフォーマンス カウンターを使用して](../../adapters-and-accelerators/adapter-sap/use-performance-counters-with-the-sap-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk adapter 用 mySAP Business Suite のアーキテクチャの概要](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)