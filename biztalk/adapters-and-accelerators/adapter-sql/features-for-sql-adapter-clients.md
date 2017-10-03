---
title: "SQL アダプタのクライアントの機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f638154b-0a09-4f89-9c52-2a62fafec7dc
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0d1df3a7d5c5748db4b0d3f365d80d84ff1f670
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="features-for-sql-adapter-clients"></a>SQL アダプタのクライアントの機能
トピックで説明されている機能だけでなく[概要の BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)では、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]アダプター クライアント用の便利な次の機能も提供します。  
  
-   **バインドのプロパティを使用してアダプターを構成するためのサポート**です。 アダプターのクライアントを構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を特定のバインディング プロパティを指定します。 たとえば、クライアントが、接続の最大数で許可されている接続プール内の特定の接続文字列の設定を指定できます、 **MaxConnectionPoolSize**プロパティをバインドします。 詳細については、次を参照してください。 [BizTalk Adapter for SQL Server アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)です。  
  
-   **操作のパラメーターに null 値のサポート**です。 アダプターのクライアントは、XSD"nillable"属性を使用して操作のパラメーターを null 値を指定できます。  
  
-   **BizTalk で動的ポートのサポート**です。 BizTalk を通じて[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]からのメッセージの動的なルーティングできるようにする動的なポートをサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキスト プロパティに基づきます。 詳細については、次を参照してください。[動的ポートを構成する](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md)です。  
  
-   **パフォーマンス カウンターのサポート**です。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントで使用する WCF ベースのパフォーマンス カウンターをサポートしています。 パフォーマンス カウンターの詳細については、次を参照してください。 [SQL アダプターで使用するパフォーマンス カウンター](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for SQL Server の概要](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)