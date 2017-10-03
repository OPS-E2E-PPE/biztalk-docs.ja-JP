---
title: "Oracle データベースでの LOB データ型のサポートをストリーミング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- streaming, node-value
- streaming
- LOB data
- streaming, node
ms.assetid: a4943cdf-8336-48ac-b592-52ec514e7300
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3f052b5051e511179ed0a3b371a619b315a16af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="streaming-support-for-lob-data-types-in-oracle-database"></a>Oracle データベースでの LOB データ型のストリーミング サポート
Oracle データベースでは、ラージ オブジェクト (LOB) データ型のストリーミングをサポートします。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]LOB データ エンド ツー エンド Oracle データベースと、アダプターのクライアントの間にストリーミングできるようになりますストリーミングをサポートするメッセージ。 ただし、ストリーミングはサポートされていません同様に、すべてのプログラミング モデル間で、アダプターを使用するとします。  
  
 アダプターでは、さまざまなプログラミング モデル間で、次に示す方法エンド ツー エンド LOB データ型のストリーミングをサポートしています。  
  
|操作|WCF チャネル モデル|WCF サービスのモデル|BizTalk Server|  
|---------------|-----------------------|-----------------------|--------------------|  
|テーブル/ビューの Insert 操作|サポートされていません|サポートされていません|サポートされていません|  
|操作をテーブル/ビューの選択|Supported|サポートされていません|Supported|  
|テーブル/ビューの更新プログラムの操作|サポートされていません|サポートされていません|サポートされていません|  
|テーブル/ビューの削除操作|サポートされていません|サポートされていません|サポートされていません|  
|テーブル/ビュー ReadLOB 操作|サポートされています。ただし、ReadLOB 操作は、主にストリーミングをサポートする WCF サービス モデルで表示される、これは推奨されません WCF チャネル モデルで使用するため。 代わりに、Select 操作または SQLEXECUTE 操作を使用します。|Supported|BizTalk Server では、ReadLOB 操作はサポートされていません。 選択操作を代わりに使用します。|  
|テーブル/ビュー UpdateLOB 操作|Supported|サポートされていません|Supported|  
|SQLEXECUTE 操作|応答でサポートされています。|サポートされていません|応答でサポートされています。|  
|ストアド プロシージャと関数の操作|応答でサポートされています。|サポートされていません|応答でサポートされています。|  
|POLLINGSTMT 操作|Supported|サポートされていません|Supported|  
  
 アダプターによって LOB データ型のストリーミングのサポート方法と、アダプターでさまざまなプログラミング モデルを使用する場合のサポートについてのより包括的なについては、次を参照してください。[ラージ オブジェクト データ型をストリーミング](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter 用 Oracle Database の概要](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)