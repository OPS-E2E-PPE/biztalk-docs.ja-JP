---
title: Siebel アダプターの SiebelConnection クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, SiebelConnection
- SiebelConnection, supported properties and methods
- SiebelConnection
ms.assetid: 661d9876-4c14-4748-b05f-cc4fd1c4ebcf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fc99c2e3f019f2ddf88647b0faeb7e41644fd0e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222338"
---
# <a name="siebelconnection-class-in-the-siebel-adapter"></a>Siebel アダプターの SiebelConnection クラス
[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] 、基になるアクセス[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] `Binding`、 `ConnectionFactory`、および`Channel`Siebel システムへの接続にします。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を実装する、`DbConnection`上記をサポートするクラスの機能です。  
  
 インスタンスを使用して`Microsoft.Data.SiebelClient.SiebelClientFactory`、クライアント プログラムがのインスタンスを取得できます、 `System.Data.Common.DbConnection` Siebel システムに接続するクラス。  
  
```  
//In this example, factory is an instance of SiebelClientFactory  
DbConnection connection = factory.CreateConnection();  
```  
  
 代わりに、次の方法を使用して、接続を作成できます。  
  
```  
  
SiebelConnection connection = new SiebelConnection();  
connection.ConnectionString = connectionString;  
```  
  
 `SiebelConnection`クラスから継承`DbConnection`です。 名前空間内に存在する`Microsoft.Data.SiebelClient`です。  
  
## <a name="supported-properties"></a>サポートされているプロパティ  
 `SiebelConnection`クラスは、次をサポート`DbConnection`プロパティです。  
  
|名前|取得/設定|Description|  
|----------|--------------|-----------------|  
|**ConnectionString**|Get および Set|接続を開くために使用する文字列を取得または設定します。|  
|**データベース**|取得|接続が開かれた後に、現在のデータベースの名前または接続が開かれる前に、接続文字列で指定されたデータベース名を取得します。 これには、Siebel リポジトリ名があります。|  
|**DataSource**|取得|この接続の Siebel ゲートウェイの名前を取得します。|  
|**ServerVersion**|取得|現在のバージョンで[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]、Siebel サーバーの実際のバージョンを表していませんハード コーディングされた値を返します。|  
|**状態**|取得|接続の状態を表す文字列を取得します。 これは、3 つの値を含めることができます。 開く、切断、または終了します。|  
  
## <a name="supported-methods"></a>サポートされているメソッド  
 `SiebelConnection`クラスは、次をサポート`DbConnection`メソッドです。  
  
|名前|Description|  
|----------|-----------------|  
|**CreateDbCommand**|この保護されたメソッドは、DbCommand の新しいインスタンスを提供します。|  
|**ChangeDatabase**|このパブリック メソッドはサポートされていませんし、呼び出された場合、例外がスローされます。|  
|**開く**|WCF チャネルを作成することで、Siebel システムに接続を開きます。|  
|**[閉じる]**|WCF チャネルを閉じることで、Siebel システムへの接続を閉じます。|  
|**CreateCommand**|コマンド オブジェクトを作成します。|  
  
## <a name="see-also"></a>参照  
 [Siebel アダプターと ADO.NET インターフェイスを拡張します。](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)