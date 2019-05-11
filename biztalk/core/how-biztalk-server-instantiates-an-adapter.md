---
title: BizTalk Server がアダプターをインスタンス化する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ebe7585-5939-4142-9281-990b4849e28d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4082d9ac17ce7e97b94cd9b585eb1a6ce326f0e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344225"
---
# <a name="how-biztalk-server-instantiates-an-adapter"></a>BizTalk Server がアダプターをインスタンス化する方法
BizTalk サービスの開始時に、すべての受信アダプターがインスタンス化される場合は、1 つ以上の構成があるし、アクティブな場所を受信する限り、します。 既定では、メッセージング エンジンを使用して送信する最初のメッセージをキューからに削除するまで、送信アダプターがインスタンス化されないを送信アダプターです。 (これとも呼ばれます「レイジー作成します」)ただし、サービスのスタートアップ時に送信アダプターをインスタンス化する必要がある場合を使えば、 **InitTransmitterOnServiceStart**アダプターの機能です。 既定のレイジー作成を使用するのではなく、サービスのスタートアップに送信アダプターを作成するメッセージング エンジンに指示します。 既定のレイジー作成の方法では、アダプターがエンドポイントで構成されていない場合に使用されるシステム リソースの量を削減できます。  
  
 カスタム アダプターを作成するときに、マネージ コードを使用することをお勧めします。 ただし、ネイティブの COM コンポーネントを使用することができます。 使用して、通常の方法で COM コンポーネント、アダプターがインスタンス化される**CoCreateInstance**します。  
  
 .NET を指定する必要が、マネージ コードの**型**では構成ファイルはアセンブリのパスは省略可能です。  
  
 次の展開オプションが考えられます。  
  
|.NET の種類|アセンブリのパス|アセンブリ展開メソッド|  
|---------------|-------------------|--------------------------------|  
|[Specified]|指定なし|アセンブリと、製品ディレクトリまたは製品ディレクトリと同じ名前のサブディレクトリへの Copy アセンブリ|  
|[Specified]|指定なし|グローバル アセンブリ キャッシュ (GAC) アセンブリ|  
|[Specified]|[Specified]|指定されたディレクトリへの Copy アセンブリ|  
  
 **トラブルシューティングのヒント。** 作成できない場合に、マネージ コードを使用してアダプターを作成するときに、fuslogvw.exe ツールを使用して、解決できないアセンブリへの参照があるかを確認します。 これは、よくある間違いです。  
  
 次の図は、指定された構成に応じた、アダプターを作成するためのロジックを示しています。  
  
 ![](../core/media/initializingtheadapter.gif "InitializingTheAdapter")  
  
 次の表は、受信アダプターが構成する方法の例と方法、実行時のアセンブリを構成することがあります。  
  
|アセンブリ展開メソッド|InboundTypeName|InboundAssemblyPath|  
|--------------------------------|---------------------|-------------------------|  
|アセンブリの場所を指定します。|Microsoft.Samples.MyReceiveAdapter|C:\MyAdapter\MyAdapter.dll|  
|.NET 型の指定 (公開キー、バージョン、およびカルチャ情報を含む)|Microsoft.Samples.MyReceiveAdapter、MyReceiveAdapter、バージョン = 1.0.2510.24622、Culture = neutral, PublicKeyToken = 077cf886a2d1c020|なし|  
|GAC アセンブリ|Microsoft.Samples.MyReceiveAdapter、MyReceiveAdapter、バージョン = 1.0.2510.24622、Culture = neutral, PublicKeyToken = 077cf886a2d1c020|なし|