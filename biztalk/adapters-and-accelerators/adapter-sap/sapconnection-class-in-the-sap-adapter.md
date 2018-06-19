---
title: SAP アダプターで SAPConnection クラス |Microsoft ドキュメント
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
ms.openlocfilehash: cb5a1778fac8577efb3c3c21a10b16f47a026397
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964296"
---
# <a name="sapconnection-class-in-the-sap-adapter"></a>SAP アダプターで SAPConnection クラス
次のセクションではメソッドとプロパティの一覧表示、 **SAPConnection**クラスです。 これは、SAP アプリケーション サーバーへの ADO.NET 接続を表します。  
  
 これは、派生元**System.Data.Common.DbConnection**です。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
  
|名前|取得/設定|Description|  
|----------|--------------|-----------------|  
|**ConnectionString**|Get および Set|参照してください[SAP 接続文字列のデータ プロバイダーの種類の説明を読む](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)です。|  
|**ConnectionTimeout**|取得|サポートされていません。 0 を返します。|  
|**データベース**|取得|SAP システムの id。|  
|**DataSource**|取得|これは、SAP アプリケーション サーバー ホストの名前を返します。|  
|**ServerVersion**|取得|SAP インスタンスおよび SAP サーバー バージョンではなく、リリース番号を示します。 たとえば、ADO.NET クライアント インスタンスのリリース番号 620 で SAP サーバー バージョン 4.6 への接続は、このプロパティには 620 が表示されます。|  
|**状態**|取得|接続の状態。 サポートされている状態は次のとおりです。<br /><br /> -[System.Data.ConnectionState]<br /><br /> 閉じる<br /><br /> -<br /><br /> 接続します。|  
  
## <a name="supported-methods"></a>サポートされているメソッド  
  
|名前|Description|  
|----------|-----------------|  
|**ChangeDatabase(string)**|サポートされていません。|  
|**Close()**|SAP システムへの接続を閉じます。|  
|**CreateCommand()**|この接続に関連付けられている新しい SAPCommand を返します。|  
|**GetSchema()**|検出された SAP テーブルの一覧を取得します。 検出されたすべてのテーブルは XML ファイル SAPDiscoveredObjects.xml で利用できます。 ファイルはある\<インストール ドライブ\>: \program files \microsoft Shared\Adapters\SAP です。|  
|**GetSchema(string)**|コレクション名に基づくスキーマを取得します。 コレクション名"Tables"をサポートしています。|  
  
|名前|Description|  
|----------|-----------------|  
|**GetSchema (string、string[] など**|コレクションの名前と制約事項に基づくスキーマを取得します。 次の表は、コレクションの名前とサポートされる制限を表します。|  
  
|名前|コレクションの名前|制限|Description|  
|----------|---------------------|------------------|-----------------|  
|**GetSchema (string、string[] など**|テーブル|-|検出された SAP テーブルの一覧|  
|**GetSchema (string、string[] など**|手順|-|検出された Rfc の一覧|  
|**GetSchema (string、string[] など**|SearchRFCs|arr [0]: 検索 expr|一致する Rfc の一覧|  
|**GetSchema (string、string[] など**|ImportParameters|arr [1]: RFC 名|RFC のインポートのパラメーター|  
|**GetSchema (string、string[] など**|ImportParameterColumn|arr [1]: RFC 名<br /><br /> arr [2] パラメーター名。|パラメーターのスキーマのインポート|  
|**GetSchema (string、string[] など**|ExportParameters|arr [1]: RFC 名|エクスポートの RFC パラメーター|  
|**GetSchema (string、string[] など**|ExportParameterColumn|arr [1]: RFC 名<br /><br /> arr [2] パラメーター名。|パラメーターのスキーマをエクスポートします。|  
|**GetSchema (string、string[] など**|TableParameters|arr [1]: RFC 名|RFC のテーブルのパラメーター|  
|**GetSchema (string、string[] など**|TableParameterColumn|arr [1]: RFC 名<br /><br /> arr [2] パラメーター名。|テーブル パラメーター スキーマ|  
|**GetSchema (string、string[] など**|ChangingParameters|arr [1]: RFC 名|RFC のパラメーターを変更します。|  
|**GetSchema (string、string[] など**|ChangingParameterColumn|arr [1]: RFC 名<br /><br /> arr [2] パラメーター名。|パラメーターのスキーマを変更します。|  
|**GetSchema (string、string[] など**|列|arr [1] テーブル名。|SAP テーブル列のスキーマ|  
  
|名前|Description|  
|----------|-----------------|  
|**Open()**|接続文字列に基づく SAP 接続を開きます。|  
  
> [!NOTE]
>  その他のすべてのコレクションのエントリのテーブル、プロシージャ、および SearchRFCs コレクションのエントリを除く arr [0] のダミー値を指定する必要があります。  
  
## <a name="supported-constructors"></a>サポートされているコンス トラクター  
  
|名前|Description|  
|----------|-----------------|  
|**SAPConnection()**|SAPConnection オブジェクト インスタンスを作成します。|  
|**SAPConnection(string)**|SAP 接続文字列を受け入れます。 接続文字列が有効でない場合は、例外をスローします。|  
  
## <a name="see-also"></a>参照  
 [SAP アダプターと ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)