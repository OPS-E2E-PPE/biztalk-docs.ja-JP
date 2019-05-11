---
title: Oracle データベースで LOB データ型に対するストリーミング サポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- streaming, node-value
- streaming
- LOB data
- streaming, node
ms.assetid: a4943cdf-8336-48ac-b592-52ec514e7300
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a6e5f842efd8c5d4778d5920c82f99302c82ec7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375966"
---
# <a name="streaming-support-for-lob-data-types-in-oracle-database"></a>Oracle データベースで LOB データ型のストリーミング サポート
Oracle データベースでは、ラージ オブジェクト (LOB) データ型ストリーミングをサポートします。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サポート メッセージ ストリーミング、LOB データ エンド ツー エンド、Oracle データベースと、アダプター クライアントの間にストリーミングすることができます。 ただし、ストリーミングがサポートされていません同様に、すべてのプログラミング モデル間でアダプターを使用する場合。  
  
 次に示す方法エンド ツー エンドの LOB データ型のストリーミングは、さまざまなプログラミング モデル間で、アダプターによってサポートされます。  
  
|操作|WCF チャネル モデル|WCF サービス モデル|BizTalk Server|  
|---------------|-----------------------|-----------------------|--------------------|  
|テーブル/ビューの挿入操作|サポートされていません|サポートされていません|サポートされていません|  
|テーブル/ビューの選択の操作|Supported|サポートされていません|Supported|  
|テーブル/ビューの更新操作|サポートされていません|サポートされていません|サポートされていません|  
|テーブル/ビューの削除の操作|サポートされていません|サポートされていません|サポートされていません|  
|テーブル/ビュー ReadLOB 操作|サポートされています。ただし、ReadLOB 操作は、WCF サービス モデルでは、ストリーミングをサポートするには、主に表示される、これは推奨されません WCF チャネル モデルで使用するため。 代わりに、選択操作または SQLEXECUTE 操作を使用します。|Supported|BizTalk Server では、ReadLOB 操作はサポートされていません。 選択操作を代わりに使用します。|  
|テーブル/ビュー UpdateLOB 操作|Supported|サポートされていません|Supported|  
|SQLEXECUTE 操作|応答でサポートされています|サポートされていません|応答でサポートされています|  
|ストアド プロシージャと関数の操作|応答でサポートされています|サポートされていません|応答でサポートされています|  
|POLLINGSTMT 操作|Supported|サポートされていません|Supported|  
  
 アダプターによって LOB データ型のストリーミングをサポートする方法と、アダプターを使用したさまざまなプログラミング モデルを使用する場合のサポートについての詳細については、次を参照してください。[ラージ オブジェクト データ型のストリーミング](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for Oracle Database の概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)