---
title: チェックリスト:サイド バイ サイド バージョン管理を使用してアプリケーションの更新 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3adee8da-18d4-4b9e-a22e-148b90d18179
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9311dca6c14ea520dfbef35b603968b0c338b484
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242572"
---
# <a name="checklist-updating-an-application-using-side-by-side-versioning"></a>チェックリスト:サイド バイ サイド バージョン管理を使用してアプリケーションの更新
次のチェックリストでは、サイド バイ サイドで実行される BizTalk アプリケーションの更新バージョンをデプロイするプロセスを既存のバージョン。  
  
 サイド バイ サイドでインストールでは、アプリケーションのアップグレードのロールアウトを段階的することができます。 利用できるインストール ビジネス パートナーのサブセットにすべてのパートナーにではなく、最初に、一度にします。 このアプローチを使用してサービスがまだ使用していない新しいバージョンが完全に新しいバージョンに移動する準備ができるまで、ユーザーに既存のアプリケーションの実行を継続することができます。  
  
 2 つのサイド バイ サイドでアプリケーションが受信する必要がありますで 2 つの異なるメッセージの受信場所。 その結果、サイド バイ サイドでアプリケーションを実行する求める必要があります、取引先パートナー アプリケーションの新しいバージョンを使用して、新しいバージョンで処理するように受信場所、新しいメッセージを送信する必要があります。 前にメッセージを受信場所、古いバージョンを使用する必要がある取引送信する必要があります。  
  
|手順|リファレンス|  
|-----------|---------------|  
|作成し、バージョン管理戦略を実装します。|「バージョン管理」のセクションで[アプリケーション更新のベスト プラクティス](../technical-guides/best-practices-for-updating-applications.md)します。|  
|アプリケーションの新しいバージョンにデプロイするプロジェクトに必要な変更を加えます。|-   [成果物を追加または作成する方法](http://go.microsoft.com/fwlink/?LinkID=154724)(http://go.microsoft.com/fwlink/?LinkID=154724)します。<br />-   [アイテムの管理](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID=154725)します。<br />-   [バインド ファイルとアプリケーションの展開](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID=154726)します。<br />-   [成果物をアプリケーションに追加します。](../technical-guides/adding-artifacts-to-an-application.md)|  
|各アセンブリのバージョン番号をインクリメントします。|[アセンブリを更新する方法](../technical-guides/how-to-update-an-assembly.md)|  
|(コピー先のアプリケーションの設定とグローバル アセンブリ キャッシュ (GAC) にインストールを有効にする) のソリューションでは、各プロジェクトの配置プロパティを設定します。|[アセンブリを更新する方法](../technical-guides/how-to-update-an-assembly.md)|  
|開発環境でアプリケーションに変更されたアセンブリが含まれるソリューションをデプロイします。|-   [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)します。<br />-   [Visual Studio から BizTalk アセンブリを再デプロイする方法](http://go.microsoft.com/fwlink/?LinkID=154720)(http://go.microsoft.com/fwlink/?LinkID=154720)します。<br />-   [アセンブリを展開します。](../technical-guides/deploying-an-assembly.md)|  
|新しい受信ポートとパートナーにメッセージを送信する新しい Url を指定する場所のいずれかの必要な受信します。<br /><br /> 必要に応じて、適切な送信ポートを作成します。<br /><br /> 必要に応じて、バインドを新しく作成された新しいアプリケーションが受信および送信ポート、および、アプリケーションの動作をテストします。|-   [作成する方法、受信ポート](http://go.microsoft.com/fwlink/?LinkId=154843)(http://go.microsoft.com/fwlink/?LinkId=154843)します。<br />-   [作成する方法、受信場所](http://go.microsoft.com/fwlink/?LinkId=154844)(http://go.microsoft.com/fwlink/?LinkId=154844)します。<br />-   [送信ポートを作成する方法](http://go.microsoft.com/fwlink/?LinkId=154845)(http://go.microsoft.com/fwlink/?LinkId=154845)します。<br />-   [アプリケーションを構成する方法](http://go.microsoft.com/fwlink/?LinkId=154847)(http://go.microsoft.com/fwlink/?LinkId=154847)します。|  
|開発環境から .msi ファイルに新しいアプリケーションをエクスポートします。|-   [BizTalk アプリケーションのエクスポート方法](http://go.microsoft.com/fwlink/?LinkId=154848)(http://go.microsoft.com/fwlink/?LinkId=154848)します。<br />-   [バインド ファイルとアプリケーションの展開](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID=154726)します。<br />-   [アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [バインド ファイルにバインドをエクスポートする方法](../technical-guides/how-to-export-bindings-to-a-binding-file.md)|  
|アプリケーションの .msi ファイルを実稼働環境で BizTalk グループにインポートします。|-   [BizTalk アプリケーションをインポートする方法](http://go.microsoft.com/fwlink/?LinkId=154827)(http://go.microsoft.com/fwlink/?LinkId=154827)します。<br />-   [BizTalk アプリケーションをインストールする方法](http://go.microsoft.com/fwlink/?LinkID=154728)(http://go.microsoft.com/fwlink/?LinkID=154728)します。<br />-   [アプリケーションを .msi ファイルからインポートする方法](../technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-   [バインド ファイルからバインドをインポートする方法](../technical-guides/how-to-import-bindings-from-a-binding-file.md)|  
|アプリケーションの完全なスタートを実行します。|-   [BizTalk アプリケーション開始および停止方法](http://go.microsoft.com/fwlink/?LinkID=154729)(http://go.microsoft.com/fwlink/?LinkID=154729)します。<br />-   [BizTalk アプリケーション展開のテスト作業](http://go.microsoft.com/fwlink/?LinkId=154825)(http://go.microsoft.com/fwlink/?LinkId=154825)します。|  
|新しい Url にメッセージを送信を開始する必要があります、パートナーに通知します。 パートナーがこれを実行すると、アプリケーションによって指定したパートナーに対するメッセージの処理が開始されます。|-|