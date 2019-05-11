---
title: Web サービスの配列を使用する方法 |Microsoft Docs
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
ms.openlocfilehash: f783c8521d1fbfbf3ffa9297f970ab54e90ce313
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385671"
---
# <a name="how-to-consume-web-service-arrays"></a>Web サービスの配列を使用する方法
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] BizTalk オーケストレーションから Web サービスで公開されている配列を使用する機能を提供します。  
  
 **Web サービスで公開される配列を使用するオーケストレーションを構成するには。**  
  
 配列を公開する Web サービスの URL を決定します。 これは、通常、Web サービスでサポートされる操作を一覧表示する asmx Web ページです。 たとえば、「 http://localhost/ArrayWS/ArraySvc.asmx」のように入力します。  
  
1.  オーケストレーションを含む Visual Studio プロジェクトでこの URL に Web 参照を追加します。  
  
    -   ソリューション エクスプ ローラーで右クリックして**参照**、 をクリック**サービス参照の追加**します。  
  
    -   **サービス参照の追加**ダイアログ ボックスで、をクリックして**詳細**します。  
  
    -   **サービス参照設定**ダイアログ ボックスで、をクリックして**Web 参照の追加**で、**互換性**セクション。  
  
    -   **Web 参照の追加** ダイアログ ボックスに Web サービスの URL を入力、 **URL**テキスト ボックスをクリック**移動**。  
  
    -   Web 参照の名前を入力、 **Web 参照名**テキスト ボックスをクリックして、**参照の追加**ボタンをクリックします。  
  
    -   Web 参照は、下に表示されます**Web 参照**ソリューション エクスプ ローラー。  
  
        > [!TIP]
        >  Web 参照をプロジェクトに追加した後、 **Web 参照の追加**プロジェクト名を右クリックすると、コマンドは直接利用または**参照**または**のWeb参照**.  
  
2.  Web ポートをオーケストレーションに追加します。  
  
    -   ドラッグ、**ポート**を起動するには、オーケストレーション デザイナーで、ツールボックスから図形をポートのいずれかを明らかになります、**ポート構成ウィザード**します。 をクリックして、**次**ボタン、**ポート構成ウィザード**を表示する、**ポートのプロパティ**ダイアログ。  
  
    -   値を入力、**名前**、ポートを特定し、をクリックするテキスト ボックス、 **[次へ]** を表示するボタン、**ポートの種類を選択**ダイアログ。  
  
    -   オプションを選択して**既存のポートの種類を使用して**、Web に対応する型参照を追加して、をクリックして、Web ポートの選択、 **[次へ]** を表示するボタン、**ポートのバインド**ダイアログ。  
  
    -   **ポートのバインド**ダイアログは、適切な選択**ポートのバインド**オプションを選択し、をクリックして、**次**、クリックして、**完了**ボタンをクリックします。 これで、Web サービスでサポートされている操作を含むオーケストレーション デザイナーに表示される Web ポートが必要です。  
  
3.  追加**送信**と**受信**を適切なオーケストレーションに図形。  
  
    -   ドラッグ、**送信**Web ポートに要求メッセージを送信するオーケストレーションを構成するオーケストレーション デザイナー画面の区分線にツールボックスから図形。 接続する場合、**送信**図形をいずれかの Web ポートの要求メッセージ コネクタ、BizTalk は自動的にこのポートに要求メッセージを送信するときに使用するには、適切な種類のメッセージを作成します。  
  
    -   ドラッグ、**受信**Web ポートから応答メッセージを受信するオーケストレーションを構成するオーケストレーション デザイナー画面の区分線にツールボックスから図形。 接続する場合、**受信**図形を Web ポートの応答メッセージ コネクタのいずれかが自動的に作成され、このポートから応答メッセージを受信するときに使用するには、適切な種類のメッセージ。  
  
> [!NOTE]
>  メッセージを送信または Web サービスからメッセージを受信するには、SOAP アダプターを使用します。 SOAP アダプターの構成の詳細については、次を参照してください。 [SOAP アダプターを構成する](../core/configuring-the-soap-adapter.md)します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]オーケストレーション エンジンは、両方のいずれかの Web サービスによって公開されている次元配列およびジャグ配列を使用するためのサポートを提供します。 配列を公開する Web サービスへの Web 参照を追加する場合、オーケストレーション デザイナーは、配列を記述した Web メッセージの種類を生成します。 送信し、他のメッセージと同様、この種類のメッセージを受信できます。 BizTalk Server では、Web ポートだけに配列を含む Web メッセージの送信は制限されません。  
  
 Web サービスの配列を使用する例を参照してください、SDK サンプル「Web サービスを使用する"と"消費 Web サービスの配列パラメーター" [ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションでのメッセージの使用](../core/using-messages-in-orchestrations.md)