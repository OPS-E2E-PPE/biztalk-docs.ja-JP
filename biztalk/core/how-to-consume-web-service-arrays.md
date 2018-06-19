---
title: Web サービスの配列を使用する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, Web services
- Web services, arrays
- orchestrations, Web services
- orchestrations, Web ports
ms.assetid: 29ecaaed-aa8a-4cf9-a7c8-4b0d6dd412ac
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e78f12405c9c331a888a268d39e2a1520c84fdc8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249898"
---
# <a name="how-to-consume-web-service-arrays"></a>方法: Web サービスの配列を使用する
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、BizTalk オーケストレーションから Web サービスで公開される配列を使用できます。  
  
 **Web サービスで公開される配列を使用するオーケストレーションを構成します。**  
  
 配列を公開する Web サービスの URL を設定します。 通常は、Web サービスでサポートされる操作が一覧表示される ASMX Web ページです。 例: http://localhost/ArrayWS/ArraySvc.asmx です。  
  
1.  オーケストレーションを含む Visual Studio プロジェクトで、この URL に Web 参照を追加します。  
  
    -   ソリューション エクスプ ローラーで右クリック**参照**、 をクリック**サービス参照の追加**です。  
  
    -   **サービス参照の追加**ダイアログ ボックスで、をクリックして**詳細**です。  
  
    -   **サービス参照設定**ダイアログ ボックスで、をクリックして**Web 参照の追加**で、**互換性**セクションです。  
  
    -   **Web 参照の追加** ダイアログ ボックスに Web サービスの URL を入力、 **URL**テキスト ボックスに入力し**移動**です。  
  
    -   Web 参照の名前を入力、 **Web 参照名**テキスト ボックスをクリック、**参照の追加**ボタンをクリックします。  
  
    -   Web 参照が表示されます**Web 参照**ソリューション エクスプ ローラー。  
  
        > [!TIP]
        >  Web 参照をプロジェクトに追加した後、 **Web 参照の追加**プロジェクト名を右クリックすると、コマンドを直接使用できますか**参照**または**のWeb参照**.  
  
2.  オーケストレーションを Web ポートを追加します。  
  
    -   ドラッグ、**ポート**を起動するオーケストレーション デザイナーで、ツールボックスから図形をポートのいずれかを表示、**ポート構成ウィザード**です。 をクリックして、**次**ボタンをクリックして、**ポート構成ウィザード**を表示する、**ポートのプロパティ**ダイアログ。  
  
    -   値を入力して、**名前**テキスト ボックスに、ポートを特定し、をクリックして、 **[次へ]** を表示するボタン、**ポートの種類を選択**ダイアログ。  
  
    -   オプションを選択して**既存のポートの種類を使用して**、Web に対応する型が参照を追加して、をクリックして、Web ポートを選択して、 **[次へ]** を表示するボタン、**ポートのバインド**ダイアログ。  
  
    -   **ポートのバインド**ダイアログを適切な選択**ポートのバインド**オプションし、をクリックして、**次** ボタン、をクリックして、**完了**ボタンをクリックします。 これで、オーケストレーション デザイナーに、Web サービスでサポートされる操作を含む Web ポートが表示されます。  
  
3.  追加**送信**と**受信**を適切なオーケストレーションに図形。  
  
    -   ドラッグ、**送信**を区分線を Web ポートに要求メッセージを送信するオーケストレーションを構成するオーケストレーション デザイナー画面で、ツールボックスから図形です。 接続している場合、**送信**図形を Web ポートのいずれかの要求メッセージ コネクタ、BizTalk が自動的にこのポートに要求メッセージを送信するときに使用するには、適切な種類のメッセージを作成します。  
  
    -   ドラッグ、**受信**を区分線を Web ポートから応答メッセージを受信するオーケストレーションを構成するオーケストレーション デザイナー画面で、ツールボックスから図形です。 接続している場合、**受信**図形 Web ポートの応答メッセージ コネクタに、BizTalk が自動的に作成このポートから応答メッセージを受信するときに使用するには、適切な種類のメッセージ。  
  
> [!NOTE]
>  SOAP アダプターを使用して、Web サービスとメッセージの送受信を行います。 SOAP アダプターの構成の詳細については、次を参照してください。 [SOAP アダプタを構成する](../core/configuring-the-soap-adapter.md)です。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーション エンジンは、両方のいずれかの Web サービスによって公開されている次元配列およびジャグ配列を使用するためサポートを提供します。 配列を公開する Web サービスに Web 参照を追加すると、オーケストレーション デザイナーによって、配列を記述した Web メッセージが生成されます。 他のメッセージと同様に、この種類のメッセージを送受信することができます。 BizTalk Server は、配列を含む Web メッセージの送信を Web ポートだけに限定しているわけではありません。  
  
 Web サービスの配列の使用の例を参照してください、SDK サンプル「Web サービスを使用する"と"消費 Web サービスの配列パラメーター"で[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)です。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションでメッセージの使用](../core/using-messages-in-orchestrations.md)