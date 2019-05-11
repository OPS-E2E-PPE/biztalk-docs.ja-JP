---
title: メッセージのカスタム例外ハンドラーのサンプルを永続化を実行している |。Microsoft Docs
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
ms.openlocfilehash: 4ba7ef5fda253f4dc96d4e29a109d0bb0c576cee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242734"
---
# <a name="running-the-message-persisting-custom-exception-handler-sample"></a>メッセージのカスタム例外ハンドラーのサンプルを永続化を実行しています。
メッセージの永続化カスタム例外ハンドラーのサンプルでは、エラー メッセージを受信、格納、およびディスクのファイルとしてファイル システムに書き込む、Microsoft BizTalk メッセージの抽出を疎結合の一般的なハンドラーを示します。  
  
 サンプルでは、オーケストレーションでカスタム例外ハンドラーを使用する方法を示します。 オーケストレーション (EAIProcess.odx) でプロセスには、エラーが発生すると、例外ハンドラーが生成し、ESB エラー メッセージがパブリッシュされます。 このエラー メッセージにはでそのペイロードで (と、BizTalk に関連するコンテキスト プロパティを含む)"インフライト"に含まれていたメッセージが含まれます、BizTalk オーケストレーション エンジンによってキャッチ、現在の System.Exception インスタンスと、例外が発生します。 この場合、「拒否」メッセージと"Approved"メッセージが、エラー メッセージを永続化されます。  
  
 EAIGenericHandler.odx、これが分離された方法で配置され、カスタム例外ハンドラーとして機能する、という名前の 2 番目のオーケストレーションは EAIGenericHandler.odx オーケストレーションで生成された特定のエラー コードをサブスクライブし、エラー メッセージを使用します。 この例外ハンドラーが (型のないドキュメント) として元のメッセージを抽出し、System.Exception インスタンスは当初、エラー メッセージに永続化します。  
  
 メッセージの永続化カスタム例外ハンドラーのサンプルは、このサンプルで使用する EAIGenericHandler.odx オーケストレーションでは、フォールトの発行で使用されるスキーマには、依存関係はありません点で、修復と再送信のカスタム例外ハンドラーのサンプルとは異なります。オーケストレーション プロセス (EAIProcess.odx)。 具体的には、EAIGenericHandler.odx オーケストレーションは、EAIProcess.odx オーケストレーションで使用されるスキーマに基づいて、型指定されたメッセージではなく System.Xml.XmlDocument インスタンスとして、エラー メッセージから元のメッセージを取得します。 また、コードを簡単に列挙するコレクションとして、メッセージを返します。  
  
 カスタム例外ハンドラー (EAIGenericHandler.odx) では、ファイル システムの場所 \Source\Samples\Exception Handling\Test\Filedrop\EAIGenericHandler.PostTmpMsg に"Denied"と"Approved"メッセージの両方をし、書き込みます。  
  
 さらに、すべてをという名前の汎用的な送信ポートがあります。一部としてインストールされている、GlobalFaultProcessor パイプラインを使用するように構成 Exceptions_FILE、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]例外管理フレームワーク。 このポートが、システムではすべての例外をサブスクライブ、両方の BizTalk は、メッセージのメッセージをルーティングし、ESB エラー メッセージが失敗しました。 例外管理フレームワークでは、それらすべてを 1 つの形式に正規化し、場所 \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions を Microsoft InfoPath 処理命令を使用してそれらをシリアル化します。  
  
## <a name="installation"></a>インストール  
 すべての例外管理サンプルでは、同じコア サービスと BizTalk アプリケーションのアイテムのセットを使用します。 そのため、すべての例外管理サンプルを実行できる例外管理サンプル アイテム 1 回だけをインストールする必要があります。 例外管理サンプルをインストールする方法については、次を参照してください。[例外管理サンプルをインストールする](../esb-toolkit/installing-the-exception-management-samples.md)します。  
  
## <a name="running-the-sample-application"></a>サンプル アプリケーションを実行します。  
 **メッセージの永続化カスタム例外ハンドラーのサンプルを実行するには**  
  
1.  最初にこのサンプルを実行する前に、受信場所と送信ポートの URL を指している \Source\Samples\Exception Handling\Test\Filedrop フォルダーに適切なディレクトリを確認します。 受信場所が EAIProcess.RequestPort、フォルダーを指定し、送信ポートの URL は EAIGenericHandler.PostTmpMsg フォルダーを指定する必要があります。  
  
2.  GlobalBank.ESB アプリケーションが実行されていない場合は、BizTalk 管理コンソールを使用して開始します。  
  
3.  \Source\Samples\Exception Handling\Test\Data フォルダーの EAIProcess.RequestPort_FILE 受信場所の指定したフォルダーにある Request_EAIGenericHandler.xml をという名前のサンプル ファイルをコピーして、サンプルを開始する: \Source\Samples\例外 Handling\Test\Filedrop\EAIProcess.RequestPort します。  
  
4.  (\Source\Samples\Exception Handling\Test\Filedrop\ フォルダー) 内の EAIGenericHandler.PostTmpMsg をという名前のフォルダーを開きます。 元のメッセージが表示されます。  
  
## <a name="how-the-sample-works"></a>サンプルのしくみ  
 メッセージを送信するには、EAIProcess オーケストレーションがアクティブにします。 では、EAIProcess オーケストレーションでメッセージを処理するときに、単価で 1 を除算しようとします。 単価はゼロであるため、0 除算の例外が発生します。 オーケストレーションのイベント ハンドラーのコードでは、この例外をキャッチし、エラー メッセージを作成します。 メッセージの注文数量は 10 未満、ビジネス ロジックでは、この例外にによって決まります、 **FaultCode**フィールドの値の**2000**します。  
  
 EAIProcess オーケストレーションをし、直接バインドされたポートを通じて BizTalk メッセージ ボックスに、エラー メッセージを発行し、オーケストレーションが終了します。  
  
 メッセージにサブスクライブする、EAIGenericHandler という名前のカスタム エラー ハンドラー オーケストレーション、 **FaultCode**フィールドの値の**2000**、新しいエラー メッセージを取得します。 オーケストレーション内のコードでは、例外 (フォールト) メッセージからすべてのメッセージを抽出し、ディスク ファイルに書き込みます。