---
title: Oracle データベース アダプター クライアントの機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f369c3a0689898bafb5383e333b980398054d0ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376730"
---
# <a name="features-for-oracle-database-adapter-clients"></a>Oracle データベース アダプター クライアントの機能
トピックで説明されている機能だけでなく[概要の BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントに役立つ次の機能も提供します。  
  
- **バインドのプロパティを使用してアダプターを構成するためのサポート**します。 アダプター クライアントを構成することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]特定のバインド プロパティを指定しています。 クライアントが、ODP.NET 接続プールを設定して使用するアダプターを構成するなど、 **UseOracleConnectionPool**プロパティをバインドします。 詳細については、次を参照してください。 [for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)します。  
  
- **操作のパラメーターに null 値のサポート**します。 アダプター クライアントでは、入力 XML の"nil"属性を使用して操作のパラメーターの null 値を指定できます。  
  
- **BizTalk で動的ポートのサポート**します。 BizTalk から[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]からのメッセージの動的ルーティングできるようにする動的ポートをサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキスト プロパティに基づきます。 詳細については、次を参照してください。[動的ポートを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-dynamic-ports-in-the-oracle-database-adapter.md)します。  
  
- **パフォーマンス カウンターのサポート**します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプター クライアントで使用するための WCF ベースのパフォーマンス カウンターをサポートしています。 パフォーマンス カウンターの詳細については、次を参照してください。[パフォーマンス カウンター](../../core/performance-counters.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle Database の概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)