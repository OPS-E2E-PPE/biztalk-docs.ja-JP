---
title: "Oracle データベース アダプターのクライアントの機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data streaming, support for
- binding properties
- adapter, features
- adapters, configuring
- message versioning, support for
- XML data streaming
- performance counters, support for
- dynamic ports in BizTalk, support for
- data streaming
ms.assetid: 63b52573-80a5-4206-95c3-478b86718fee
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b120c948ef3d9821af0a79e91fd718e3a1f33137
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="features-for-oracle-database-adapter-clients"></a>Oracle データベース アダプターのクライアントの機能
トピックで説明されている機能だけでなく[概要の BizTalk Adapter 用 Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアント用の便利な次の機能も提供します。  
  
-   **バインドのプロパティを使用してアダプターを構成するためのサポート**です。 アダプターのクライアントを構成することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を特定のバインディング プロパティを指定します。 クライアントが設定して、ODP.NET 接続プールを使用するアダプターを構成するなど、 **UseOracleConnectionPool**プロパティをバインドします。 詳細については、次を参照してください。 [Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。  
  
-   **操作のパラメーターに null 値のサポート**です。 アダプターのクライアントは、入力 XML ファイルの"nil"属性を使用して操作のパラメーターを null 値を指定できます。  
  
-   **BizTalk で動的ポートのサポート**です。 BizTalk を通じて[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]からのメッセージの動的なルーティングできるようにする動的なポートをサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキスト プロパティに基づきます。 詳細については、次を参照してください。[動的ポートを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-dynamic-ports-in-the-oracle-database-adapter.md)です。  
  
-   **パフォーマンス カウンターのサポート**です。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントで使用する WCF ベースのパフォーマンス カウンターをサポートしています。 パフォーマンス カウンターの詳細については、次を参照してください。[パフォーマンス カウンター](../../core/performance-counters.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter 用 Oracle Database の概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)