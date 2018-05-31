---
title: カスタム例外ハンドラーのサンプルを保持するメッセージを実行している |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0a4c819-f6bd-4dea-8be9-e3006337665f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6d7927357e4c2be03ecd8b2e77d45558b5bc692
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295330"
---
# <a name="running-the-message-persisting-custom-exception-handler-sample"></a>カスタム例外ハンドラーのサンプルを保持するメッセージを実行しています。
メッセージの永続化のカスタム例外ハンドラーのサンプルでは、エラー メッセージを受信、これらの格納、およびファイル システムにディスク ファイルとして書き込みます Microsoft BizTalk メッセージを抽出する疎結合、ジェネリック ハンドラーを示します。  
  
 サンプルは、オーケストレーションでのカスタム例外ハンドラーを使用する方法を示します。 オーケストレーション (EAIProcess.odx) でプロセスには、エラーが発生すると、例外ハンドラーが生成し、ESB フォールト メッセージを公開します。 このエラー メッセージにはでそのペイロードに"インフライト"であった (と、BizTalk に関連するコンテキスト プロパティを含む) メッセージが含まれます、BizTalk オーケストレーション エンジンによってキャッチされた現在の System.Exception インスタンスだけでなく、例外が発生します。 この問題が発生すると、「拒否」メッセージと"Approved"メッセージが、エラー メッセージに永続化されます。  
  
 EAIGenericHandler.odx、分離された方法が展開されており、カスタム例外ハンドラーとして機能し、これをという名前の 2 番目のオーケストレーションは EAIGenericHandler.odx オーケストレーションで生成された特定のエラー コードをサブスクライブし、エラー メッセージを使用します。 この例外ハンドラーが (型のないドキュメント) として元のメッセージを抽出し、System.Exception インスタンスは当初、エラー メッセージに永続化します。  
  
 メッセージの永続化のカスタム例外ハンドラーのサンプルは、このサンプルで使用する EAIGenericHandler.odx オーケストレーションでは、フォールトの発行に使用されるスキーマには、依存関係はありません点で、修復と再送信のカスタム例外ハンドラーのサンプルとは異なります。オーケストレーション プロセス (EAIProcess.odx)。 具体的には、EAIGenericHandler.odx オーケストレーションは、EAIProcess.odx オーケストレーションで使用されるスキーマに基づいて、型指定されたメッセージではなく System.Xml.XmlDocument インスタンスとして、エラー メッセージから元のメッセージを取得します。 また、コードを簡単に列挙できるコレクションとしてメッセージを返します。  
  
 カスタム例外ハンドラー (EAIGenericHandler.odx) では、ファイル システムの場所 \Source\Samples\Exception Handling\Test\Filedrop\EAIGenericHandler.PostTmpMsg に"Denied"と"Approved"メッセージの両方をし、書き込みます。  
  
 さらに、ALL という名前の汎用的な送信ポートがあります。一部としてインストールされている、GlobalFaultProcessor パイプラインを使用するように構成 Exceptions_FILE、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外管理フレームワーク。 このポートは、システム内のすべての例外をサブスクライブ、両方の BizTalk は、メッセージをルーティングするメッセージと ESB エラー メッセージが失敗しました。 例外管理フレームワークでは、それらをすべて 1 つの形式を正規化し、場所 \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions を Microsoft InfoPath 処理命令を使用してシリアル化します。  
  
## <a name="installation"></a>インストール  
 すべての例外管理サンプルは、同じコア サービスと BizTalk アプリケーションのアイテムのセットを使用します。 そのため、すべての例外の管理のサンプルを実行するために例外管理サンプル アイテム 1 回だけをインストールする必要があります。 例外の管理のサンプルをインストールする方法については、次を参照してください。[例外管理のサンプルをインストールする](../esb-toolkit/installing-the-exception-management-samples.md)です。  
  
## <a name="running-the-sample-application"></a>サンプル アプリケーションの実行  
 **メッセージの永続化のカスタム例外ハンドラーのサンプルを実行するには**  
  
1.  最初にこのサンプルを実行する前に、受信場所と送信ポートの URL を指している \Source\Samples\Exception Handling\Test\Filedrop フォルダーに適切なディレクトリを確認します。 受信場所が EAIProcess.RequestPort、フォルダーを指定する必要があり、送信ポートの URL は EAIGenericHandler.PostTmpMsg のフォルダーを指定する必要があります。  
  
2.  GlobalBank.ESB アプリケーションが既に実行されていない場合は、BizTalk 管理コンソールを使用して、開始します。  
  
3.  EAIProcess.RequestPort_FILE 受信場所の指定されたフォルダーに、\Source\Samples\Exception Handling\Test\Data フォルダーにある Request_EAIGenericHandler.xml をという名前のサンプル ファイルをコピーして、サンプルを開始する: \Source\Samples\例外 Handling\Test\Filedrop\EAIProcess.RequestPort です。  
  
4.  (フォルダーにある \Source\Samples\Exception Handling\Test\Filedrop\) EAIGenericHandler.PostTmpMsg をという名前のフォルダーを開きます。 元のメッセージが表示されます。  
  
## <a name="how-the-sample-works"></a>このサンプルのしくみ  
 メッセージを送信するには、EAIProcess オーケストレーションがアクティブにします。 では、EAIProcess オーケストレーションでは、メッセージを処理するとき、単価で 1 を除算しようとします。 単価はゼロであるため、0 除算の例外が発生します。 オーケストレーションのイベント ハンドラーのコードでは、この例外をキャッチし、エラー メッセージを作成します。 ビジネス ロジックでこの例外があるために、メッセージの注文数量は 10 未満、 **FaultCode**フィールドの値の**2000**です。  
  
 オーケストレーションが終了し、では、EAIProcess オーケストレーションが直接バインド ポートを通じて BizTalk メッセージ ボックスに、エラー メッセージを発行します。  
  
 メッセージをサブスクライブする EAIGenericHandler をという名前のカスタム エラー ハンドラー オーケストレーション、 **FaultCode**フィールドの値の**2000**、新しいエラー メッセージを取得します。 オーケストレーション内のコードでは、例外 (フォールト) メッセージからのすべてのメッセージを抽出し、ディスク ファイルに書き込みます。