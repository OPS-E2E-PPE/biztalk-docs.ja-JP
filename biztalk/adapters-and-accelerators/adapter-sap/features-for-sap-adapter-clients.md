---
title: SAP アダプター クライアントの機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 832df9dfe3384a239ab4e4148229e9bc65f65e77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373452"
---
# <a name="features-for-sap-adapter-clients"></a>SAP アダプター クライアントの機能
トピックで説明されている機能だけでなく[mySAP Business Suite の BizTalk アダプターのアーキテクチャの概要](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアントに役立つ次の機能も提供します。  
  
- **バインドのプロパティを使用してアダプターを構成するためのサポート**します。 アダプター クライアントを構成することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]特定のバインド プロパティを指定しています。 クライアントが、アダプターの接続プール内の値を指定することによって接続の最大数を指定するアダプターを構成するなど、 **MaxConnectionsPerSystem**プロパティをバインドします。 詳細については、次を参照してください。 [mySAP Business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。  
  
- **BizTalk Server で動的ポートのサポート**します。 BizTalk から[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]からのメッセージの動的ルーティングできるようにする動的ポートをサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキスト プロパティに基づきます。 詳細については、次を参照してください。[動的ポートを構成する](../../adapters-and-accelerators/adapter-sap/configure-dynamic-ports-in-the-sap-adapter.md)します。
  
- **メッセージのバージョン管理のサポート**します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]メッセージの今後のリリースでのさまざまなメッセージ スキーマのサポートを有効にバージョン管理をサポートしています、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。[メッセージ バージョン管理サポート](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md)します。  
  
  > [!NOTE]
  >  この機能は、アダプターの以前のバージョンとの下位互換性を提供しません。  
  
- **パフォーマンス カウンターのサポート**します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプター クライアントで使用するための WCF ベースのパフォーマンス カウンターをサポートしています。 パフォーマンス カウンターの詳細については、次を参照してください。 [SAP アダプターを使用したパフォーマンス カウンターを使用して](../../adapters-and-accelerators/adapter-sap/use-performance-counters-with-the-sap-adapter.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter 用 mySAP Business Suite のアーキテクチャの概要](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)