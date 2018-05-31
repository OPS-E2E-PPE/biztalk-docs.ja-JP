---
title: JD Edwards OneWorld アダプター |Microsoft ドキュメント
description: インストール、チュートリアルの手順、アーキテクチャの説明、SSO のセキュリティを使用して、アプリケーションの作成、バインド ファイルをインポートおよび BizTalk Adapter for j. d. の使用時に例外処理を追加 BizTalk Server で Edwards OneWorld
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5df8cd89-d9df-41ca-9a2c-b9d7fbcd06f2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bde93503bff679faf2717edefb386aa2f43fc3e
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015931"
---
# <a name="jd-edwards-oneworld-adapter"></a>JD Edwards OneWorld アダプタ
Microsoft BizTalk Adapter for JD Edwards OneWorld により、JD Edwards OneWorld のビジネス関数を BizTalk Server で利用することが可能になります。 ここでは、JD Edwards OneWorld 固有の情報にアクセスするように BizTalk Adapter for JD Edwards OneWorld を設定する方法について説明します。  
  
## <a name="get-started"></a>作業を開始します。 
[開始](../core/getting-started-with-biztalk-adapter-for-jd-edwards-oneworld.md)アダプターをインストールし、ステップ チュートリアルを実行する手順について説明します。

## <a name="architecture"></a>Architecture
[アーキテクチャ](../core/planning-and-architecture17.md)アダプターのしくみ、どのインスタンスと関数がプールされており、デザイン時および実行時の制限事項にクエリと取得を一覧表示する場合、について詳しく説明し、このアダプターで複数の注文のアイテムを使用します。

## <a name="security"></a>セキュリティ
[BizTalk Adapter for JD Edwards OneWorld セキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)BizTalk Serer このアダプターを使用するアプリケーションをセキュリティで保護するには、エンタープライズ シングル サインオン (SSO) を使用します。

## <a name="create-the-artifacts"></a>成果物を作成します。
[アプリケーションのアイテムを作成する](../core/developing-applications3.md)Visual Studio および BizTalk 管理コンソールで、アイテムを追加する方法を示します。 また、オーケストレーションでメッセージ コンテキスト プロパティを使用する方法も示しています。

## <a name="import-your-app"></a>アプリをインポートします。
[BizTalk Adapter for JD Edwards OneWorld の展開](../core/deploying-biztalk-adapter-for-jd-edwards-oneworld.md)BizTalk 管理コンソールにアプリケーションのバインド ファイルをインポートする方法について説明し、制限事項経由で送信します。 

## <a name="exception-handling"></a>例外処理 
[BizTalk Server 例外処理](../core/using-biztalk-server-exception-handling1.md)jdearglist.txt ファイルを更新し、例外を処理するオーケストレーションを別の図形の追加に関するガイダンスを示します。

## <a name="troubleshooting"></a>トラブルシューティング
[トラブルシューティング](../core/troubleshooting-jd-edwards-oneworld.md)一般的なエラーと状況、および Event Tracing for Windows をについて説明します。

## <a name="data-types"></a>データ型
[付録: データ型](../core/appendix-a-data-types.md)このアダプターによって使用されるサンプルのデータ型を一覧表示します。

## <a name="ui-reference"></a>UI リファレンス
[BizTalk Adapter for JDE OneWorld の UI リファレンス](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md)の詳細 ダイアログ ボックスおよびこのアダプターによって使用されるウィザードについて説明します。 