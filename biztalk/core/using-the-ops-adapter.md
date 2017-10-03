---
title: "Ops アダプタの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IOpsAIC interface
- Ops adapters, configuring
- Ops adapters, IOpsAIC interface
- process management solution tutorial, Ops adapters
- Ops adapters, processing
ms.assetid: 331f3614-e00b-4587-b82b-3c7bc394f361
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d93436e727265c4b381cdff72c42b3a677d0a4dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-ops-adapter"></a>Ops アダプタの使用
ビジネス プロセス管理ソリューションは、Ops アダプタを使用して、新しいエラー報告機能からのエラー報告を処理します。 アダプタからのメッセージを処理するサンプル ハンドラがソリューションに含まれていますが、独自のハンドラを簡単に作成して、アダプタを他のソリューションで使うことができます。 エラー報告機能については、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)です。  
  
> [!NOTE]
>  このソリューションではエラー報告用にアダプタを使用しますが、アダプタはエラー処理にだけ使用するわけではありません。 メッセージの応答で特定のオブジェクト メソッドを実行する場合、さまざまな状況でアダプタを使用できます。  
  
## <a name="how-the-ops-adapter-processes-error-reports"></a>Ops アダプタがエラー報告を処理する方法  
 エラー報告を使用するソリューション内のポート最終的には、エラー メッセージを送信する、 **BIZTALKERRORS-SP**ポートです。 ポートのフィルターがの存在を検査、 **ErrorReport.ErrorType**コンテキスト プロパティです。 エラー報告メッセージだけがこのコンテキスト プロパティを持っています。  
  
 **BIZTALKERRORS-SP**送信ポートは、エンベロープにメッセージを格納する、XML アセンブラ コンポーネントを使用するパイプラインを介して、エラー メッセージを実行します。 その後で、メッセージは Ops アダプタに送られます。  
  
 ErrorEnvelope スキーマによって定義されるエンベロープは、メッセージの種類をすべて受け入れるようにマークされています。 ただし、BizTalk グループで定義されたメッセージの種類に限られます。 未知の種類のメッセージを受け取った場合は、メッセージが保留されます。 このようなメッセージとエラーが生成されにルーティングされます、 **BIZTALKERRORS-SP**ポートです。 その結果、メッセージは既知の種類にはならないので、パイプラインの XML アセンブラ コンポーネントでエラーが発生する可能性があります。 パイプライン エラーによりメッセージが保留されます。  
  
> [!NOTE]
>  不明なメッセージの種類によるルーティング エラーを処理するには、カスタム パイプライン コンポーネントを記述および用のカスタム パイプラインのコンポーネントを使用する必要があります、 **BIZTALKERRORS-SP**ポートです。 カスタム コンポーネントは、XML アセンブラ コンポーネントを置換します。 カスタム コンポーネントを配置する必要があります、 **ErrorReport**エンベロープ ヘッダー内のプロパティとメッセージをエンベロープの本文に追加します。  
  
 Ops アダプタは、トランザクションの一方向送信アダプタです。 アダプタがメッセージを処理する場合、必要に応じて、最初に指定のアセンブリを読み込みます。 アダプタはアセンブリをメモリにキャッシュして、呼び出しごとにアセンブリを読み込むというオーバーヘッドを回避します。 指定したクラスのインスタンスを作成し、リフレクションを使用して実装するアセンブリのオブジェクトを取得、 **IOpsAIC**インターフェイスです。 これはすべてが成功した場合、アダプターを呼び出す、**初期化**メソッドを呼び出し、続いて、 **Execute**メソッド、エラー レポート メッセージを渡すことです。  
  
 エラーがある場合を呼び出す**Execute**アダプターがメッセージを再送信します。 指定したクラスを実装しない場合、 **IOpsAIC**インターフェイス、またはクラスやアセンブリが見つかりません、アダプターがメッセージを中断します。  
  
> [!TIP]
>  アダプタはリフレクションを使用するので、グローバル アセンブリ キャッシュ (GAC) 内にクラスを含むアセンブリが必要です。  
  
## <a name="the-iopsaic-interface"></a>IOpsAIC インターフェイス  
 アダプターを実装するオブジェクトが必要です、 **IOpsAIC**インターフェイスです。 インターフェイスは次のようになります。  
  
```  
interface IOpsAIC  
{  
    void Initialize(string config);  
    void Execute(byte[] message);  
}  
```  
  
 アダプターでは、元のメッセージを渡すバイト配列として、 **Execute**メソッドです。  
  
## <a name="configuring-the-adapter"></a>アダプタの構成  
 他のアダプタと同じようにアダプタを構成できます。 次の表では、アダプタの構成プロパティについて説明しています。  
  
|表示名|Description|  
|------------------|-----------------|  
|**.NET アセンブリの厳密な名前**|アセンブリの完全修飾名。|  
|**OpsAIC クラス名**|実装するアセンブリ内のクラスの名前、 **IOpsAIC**インターフェイスです。|  
|**初期化データ**|引数として渡される文字列、**初期化**クラスのメソッドです。|  
  
 アダプタにはアセンブリの完全修飾名が必要です。 完全修飾名は、アセンブリを GAC に追加するときにアセンブリに指定する名前で、 アセンブリの名前、バージョン、カルチャ、および公開キー トークンを含む文字列です。 グローバル アセンブリ キャッシュ ツールを使用して、アセンブリの完全修飾名を参照できます。  
  
 完全修飾名の詳細については、『.NET Framework 開発者ガイド』の「アセンブリ名 (Assembly Names)」を参照してください。 gacutil.exe の詳細については、『[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] 開発者ガイド』の「グローバル アセンブリ キャッシュ ツール (Gacutil.exe) (Global Assembly Cache Tool (Gacutil.exe))」を参照してください。  
  
 クラス名には名前空間を付ける必要があります。 たとえば、クラスが**OpsHandler**で、 **OperationsHandler**名前空間とクラス名を指定**OperationsHandler.OpsHandler**です。  
  
## <a name="see-also"></a>参照  
 [Ops アダプタ](../core/the-ops-adapter.md)