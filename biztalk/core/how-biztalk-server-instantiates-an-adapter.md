---
title: "BizTalk Server がアダプターにインスタンス化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ebe7585-5939-4142-9281-990b4849e28d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b32e6e40bf39c09e747391bba51a54143fc67e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-biztalk-server-instantiates-an-adapter"></a>BizTalk Server でのアダプターのインスタンス化
BizTalk サービスの開始時に、構成されてアクティブである受信場所が 1 つ以上ある場合は、すべての受信アダプターがインスタンス化されます。 既定では、送信アダプターによって送信される最初のメッセージをメッセージング エンジンがキューから削除するまで、送信アダプターはインスタンス化されません  (これとも呼ばれます「レイジー作成します」)ただし、サービスのスタートアップ時に送信アダプターのインスタンスを作成する必要がある場合を使えば、 **InitTransmitterOnServiceStart**アダプターの機能です。 これにより、メッセージング エンジンは既定のレイジー作成ではなく、サービスの開始時に送信アダプターを作成するようになります。 既定のレイジー作成の方法は、エンドポイントにアダプターが構成されていない場合に、システム リソースの使用量を削減する上で役立ちます。  
  
 カスタム アダプターを作成するときには、マネージ コードを使用することをお勧めします。 ただし、ネイティブ COM コンポーネントを使用することもできます。 通常の方法を使用して、COM コンポーネント、アダプターがインスタンス化される**CoCreateInstance**です。  
  
 マネージ コード用の .NET を指定する必要があります。**型**構成ファイルにあるアセンブリのパスは省略可能です。  
  
 使用できる展開オプションは、次のとおりです。  
  
|.NET の種類|アセンブリ パス|アセンブリ展開メソッド|  
|---------------|-------------------|--------------------------------|  
|[Specified]|指定なし|アセンブリと同じ名前を持つ、製品ディレクトリまたは製品ディレクトリ内のサブディレクトリへの Copy アセンブリ|  
|[Specified]|指定なし|グローバル アセンブリ キャッシュ (GAC) アセンブリ|  
|[Specified]|[Specified]|指定されたディレクトリへの Copy アセンブリ|  
  
 **トラブルシューティングのヒント:**作成が失敗した場合に、マネージ コードを使用してアダプターを作成するときに、fuslogvw.exe ツールを使用して、解決できないアセンブリへの参照があるかを確認します。 これはよくある間違いです。  
  
 指定された構成に応じた、アダプター作成時のロジックを次に示します。  
  
 ![](../core/media/initializingtheadapter.gif "InitializingTheAdapter")  
  
 次の表に、受信アダプターを構成する方法と、ランタイム アセンブリを構成する方法の例を示します。  
  
|アセンブリ展開メソッド|InboundTypeName|InboundAssemblyPath|  
|--------------------------------|---------------------|-------------------------|  
|アセンブリの場所の指定|Microsoft.Samples.MyReceiveAdapter|C:\MyAdapter\MyAdapter.dll|  
|.NET 型 (公開キー、バージョン、およびカルチャ情報) の指定|Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020|なし|  
|GAC アセンブリ|Microsoft.Samples.MyReceiveAdapter, MyReceiveAdapter, Version=1.0.2510.24622, Culture=neutral, PublicKeyToken=077cf886a2d1c020|なし|