---
title: SQL アダプター クライアントの機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f638154b-0a09-4f89-9c52-2a62fafec7dc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35dbd3c6236e1cd17bcfda0b083ef1309d7d9362
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369364"
---
# <a name="features-for-sql-adapter-clients"></a>SQL アダプター クライアントの機能
トピックで説明されている機能だけでなく[SQL Server 用 BizTalk アダプターの概要](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]アダプター クライアントに役立つ次の機能も提供します。  
  
- **バインドのプロパティを使用してアダプターを構成するためのサポート**します。 アダプター クライアントを構成することができます、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]特定のバインド プロパティを指定しています。 たとえば、クライアントが設定して接続プール内の特定の接続文字列の許可される接続の最大数を指定できます、 **MaxConnectionPoolSize**プロパティをバインドします。 詳細については、次を参照してください。 [for SQL Server アダプターのバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)します。  
  
- **操作のパラメーターに null 値のサポート**します。 アダプター クライアントでは、XSD"nillable"属性を使用して操作のパラメーターの null 値を指定できます。  
  
- **BizTalk で動的ポートのサポート**します。 BizTalk から[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]からのメッセージの動的ルーティングできるようにする動的ポートをサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキスト プロパティに基づきます。 詳細については、次を参照してください。[動的ポートを構成する](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md)します。  
  
- **パフォーマンス カウンターのサポート**します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプター クライアントで使用するための WCF ベースのパフォーマンス カウンターをサポートしています。 パフォーマンス カウンターの詳細については、次を参照してください。 [SQL アダプターを使用したパフォーマンス カウンターを使用して](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for SQL Server の概要](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)