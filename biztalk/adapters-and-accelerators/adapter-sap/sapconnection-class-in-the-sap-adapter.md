---
title: SAP アダプターの SAPConnection クラス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAPConnection, supported methods, classes, and constructors
ms.assetid: a700602d-8135-4f67-a38b-770357d4e28b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14fb1cf2b04fd16aedd8aa97f75f2fa57620e3f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372953"
---
# <a name="sapconnection-class-in-the-sap-adapter"></a>SAP アダプターの SAPConnection クラス
メソッドおよびプロパティを次のセクションの一覧、 **SAPConnection**クラス。 これは、SAP アプリケーション サーバーへの ADO.NET 接続を表します。  
  
 これは、派生元**System.Data.Common.DbConnection**します。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
  
|名前|Get/Set|説明|  
|----------|--------------|-----------------|  
|**ConnectionString**|Get と Set|参照してください[SAP 接続文字列のデータ プロバイダーの種類について](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)します。|  
|**ConnectionTimeout**|取得|サポートされていません。 0 を返します。|  
|**[データベース]**|取得|SAP システム id。|  
|**DataSource**|取得|これは、SAP アプリケーション サーバーのホストの名前を返します。|  
|**ServerVersion**|取得|SAP インスタンスと SAP サーバー バージョンではなくリリース番号が表示されます。 たとえば、ADO.NET クライアント インスタンスのリリース番号 620 で SAP サーバー バージョン 4.6 への接続は、このプロパティには 620 が表示されます。|  
|**State**|取得|接続の状態。 サポートされている状態は次のとおりです。<br /><br /> - [System.Data.ConnectionState]<br /><br /> クローズ<br /><br /> -<br /><br /> 接続します。|  
  
## <a name="supported-methods"></a>サポートされているメソッド  
  
|名前|説明|  
|----------|-----------------|  
|**ChangeDatabase(string)**|サポートされていません。|  
|**Close()**|SAP システムへの接続を閉じます。|  
|**CreateCommand()**|この接続に関連付けられた新しい SAPCommand を返します。|  
|**GetSchema()**|検出された SAP テーブルの一覧を取得します。 検出されたすべてのテーブルは、XML ファイル SAPDiscoveredObjects.xml に利用します。 ファイルがある\<インストール ドライブ\>: \Program Files\Common \microsoft Shared\Adapters\SAP します。|  
|**GetSchema(string)**|コレクション名に基づくスキーマを取得します。 コレクション名「テーブル」をサポートしています。|  
  
|名前|説明|  
|----------|-----------------|  
|**GetSchema(string, string[])**|コレクションの名前と制限事項に基づくスキーマを取得します。 次の表は、コレクションの名前とサポートされている制限を表します。|  
  
|名前|コレクション名|制限|説明|  
|----------|---------------------|------------------|-----------------|  
|**GetSchema(string, string[])**|テーブル|-|検出された SAP テーブルの一覧|  
|**GetSchema(string, string[])**|手順|-|検出された Rfc の一覧|  
|**GetSchema(string, string[])**|SearchRFCs|arr [0]:検索式|Rfc の照合の一覧|  
|**GetSchema(string, string[])**|ImportParameters|arr [1]:RFC 名|RFC のパラメーターをインポートします。|  
|**GetSchema(string, string[])**|ImportParameterColumn|arr [1]:RFC 名<br /><br /> arr [2]:パラメーター名|パラメーターのスキーマのインポート|  
|**GetSchema(string, string[])**|ExportParameters|arr [1]:RFC 名|エクスポートの RFC パラメーター|  
|**GetSchema(string, string[])**|ExportParameterColumn|arr [1]:RFC 名<br /><br /> arr [2]:パラメーター名|パラメーターのスキーマをエクスポートします。|  
|**GetSchema(string, string[])**|TableParameters|arr [1]:RFC 名|RFC の表のパラメーター|  
|**GetSchema(string, string[])**|TableParameterColumn|arr [1]:RFC 名<br /><br /> arr [2]:パラメーター名|パラメーターのテーブル スキーマ|  
|**GetSchema(string, string[])**|ChangingParameters|arr [1]:RFC 名|RFC のパラメーターを変更します。|  
|**GetSchema(string, string[])**|ChangingParameterColumn|arr [1]:RFC 名<br /><br /> arr [2]:パラメーター名|パラメーターのスキーマを変更します。|  
|**GetSchema(string, string[])**|列|arr [1]:テーブル名|SAP テーブル列のスキーマ|  
  
|名前|説明|  
|----------|-----------------|  
|**Open()**|接続文字列に基づいて、SAP 接続を開きます。|  
  
> [!NOTE]
>  その他のすべてのコレクション エントリ、Table、Procedure、および SearchRFCs コレクション エントリを除く arr [0] のダミー値を指定する必要があります。  
  
## <a name="supported-constructors"></a>サポートされているコンス トラクター  
  
|名前|説明|  
|----------|-----------------|  
|**SAPConnection()**|SAPConnection オブジェクト インスタンスを作成します。|  
|**SAPConnection(string)**|SAP の接続文字列を受け入れます。 接続文字列が有効でない場合は、例外をスローします。|  
  
## <a name="see-also"></a>参照  
 [SAP アダプターを使用した ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)