---
title: Ops アダプタの使用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IOpsAIC interface
- Ops adapters, configuring
- Ops adapters, IOpsAIC interface
- process management solution tutorial, Ops adapters
- Ops adapters, processing
ms.assetid: 331f3614-e00b-4587-b82b-3c7bc394f361
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b219d88ec07c63baf476cc3a3bf31775e03b2b4a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246430"
---
# <a name="using-the-ops-adapter"></a>Ops アダプタの使用
ビジネス プロセス管理ソリューションでは、Ops アダプタを使用して、新しいエラー報告機能からエラー レポートを処理します。 ソリューションは、独自に作成し、その他のソリューションでアダプターを使用できますが、簡単にサンプル ハンドラーをメッセージを処理する、アダプターから、です。 エラー報告機能については、次を参照してください。[できませんでしたメッセージのルーティングを使用して](../core/using-failed-message-routing.md)します。  
  
> [!NOTE]
>  ソリューションでは、エラー報告のアダプターを使用して、その使用はエラー処理に制限はありません。 メッセージに対する応答で特定のオブジェクトのメソッドを実行するたびに、さまざまな状況でアダプタを使用できます。  
  
## <a name="how-the-ops-adapter-processes-error-reports"></a>Ops アダプタがエラー レポートを処理する方法  
 エラー報告を使用して、ソリューション内のポートが最終的に、エラー メッセージを送信、 **BIZTALKERRORS-SP**ポート。 存在のテストをポートでフィルター処理、 **ErrorReport.ErrorType**コンテキスト プロパティ。 エラー報告メッセージだけでは、このコンテキスト プロパティがあります。  
  
 **BIZTALKERRORS-SP**送信ポートは、エンベロープにメッセージを配置する、XML アセンブラ コンポーネントを使用するパイプラインでエラー メッセージを実行します。 メッセージは Ops アダプタに移動します。  
  
 ErrorEnvelope スキーマによって定義された、エンベロープは、あらゆる種類のメッセージを受け入れるようにマークされます。 ただし、"any"は、メッセージ型で定義されている BizTalk グループ。 ソリューションが不明な種類のメッセージを受信メッセージが保留になることもします。 このようなメッセージがエラーを生成およびにルーティングされます、 **BIZTALKERRORS-SP**ポート。 さらに、メッセージはエラーを生成パイプラインの XML アセンブラー コンポーネントで既知のメッセージの種類はならないためです。 パイプラインのエラーは、メッセージを中断します。  
  
> [!NOTE]
>  不明なメッセージの種類によるルーティング エラーを処理するカスタム パイプライン コンポーネントを記述し、用のカスタム パイプラインでコンポーネントを使用する必要があります、 **BIZTALKERRORS-SP**ポート。 カスタム コンポーネントには、XML アセンブラー コンポーネントが置き換えられます。 カスタム コンポーネントを配置する必要があります、 **ErrorReport**プロパティをエンベロープ ヘッダーとメッセージをエンベロープの本文に追加します。  
  
 Ops アダプタは、トランザクションの一方向の送信アダプターです。 アダプターがメッセージを処理するときが初めて読み込まれる、指定されたアセンブリに必要な場合。 アダプターは、呼び出しごとにアセンブリを読み込むというオーバーヘッドを回避するためにメモリ内アセンブリをキャッシュします。 指定したクラスのインスタンスを作成し、リフレクションを使用して実装するアセンブリのオブジェクトを取得、 **IOpsAIC**インターフェイス。 このすべてが成功した場合は、アダプターが呼び出す、**初期化**メソッドに呼び出し、 **Execute**メソッドは、レポートのエラー メッセージを渡すことです。  
  
 エラーがある場合を呼び出す**Execute**アダプターがメッセージを再送信します。 指定したクラスが実装していない場合、 **IOpsAIC**インターフェイスまたはクラスまたはアセンブリが見つからない場合、アダプターがメッセージを中断します。  
  
> [!TIP]
>  アダプターは、リフレクションを使用するため、クラスを含むアセンブリがグローバル アセンブリ キャッシュ (GAC) にあります。  
  
## <a name="the-iopsaic-interface"></a>IOpsAIC インターフェイス  
 アダプターが実装するオブジェクトが必要です、 **IOpsAIC**インターフェイス。 インターフェイスは次のようです。  
  
```  
interface IOpsAIC  
{  
    void Initialize(string config);  
    void Execute(byte[] message);  
}  
```  
  
 アダプターでは、元のメッセージを渡しますにバイト配列として、 **Execute**メソッド。  
  
## <a name="configuring-the-adapter"></a>アダプターの構成  
 その他のアダプターの場合と同じようにアダプターを構成します。 次の表では、アダプターの構成プロパティについて説明します。  
  
|表示名|説明|  
|------------------|-----------------|  
|**.NET アセンブリの厳密な名前**|アセンブリの完全修飾名。|  
|**OpsAIC クラス名**|実装するアセンブリ内のクラスの名前、 **IOpsAIC**インターフェイス。|  
|**初期化データ**|引数として渡される文字列、**初期化**クラスのメソッド。|  
  
 アダプターが、アセンブリの完全修飾名が必要であることを確認します。 完全修飾名は、アセンブリを GAC に追加するときに指定された名前です。 完全修飾名は、アセンブリの名前、バージョン、カルチャ、および公開キー トークンを含む文字列です。 グローバル アセンブリ キャッシュ ツールを使用してアセンブリの完全修飾名を確認できます gacutil.exe します。  
  
 完全修飾アセンブリ名の詳細については、.NET Framework 開発者ガイドの「アセンブリ Names」を参照してください。 Gacutil.exe の詳細について「グローバル アセンブリ キャッシュ ツール (Gacutil.exe)」を参照してください、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]開発者ガイド。  
  
 クラス名では、名前空間を指定する必要があります。 たとえば、クラスが**OpsHandler**で、 **OperationsHandler**名前空間とクラス名を指定**OperationsHandler.OpsHandler**します。  
  
## <a name="see-also"></a>参照  
 [Ops アダプター](../core/the-ops-adapter.md)