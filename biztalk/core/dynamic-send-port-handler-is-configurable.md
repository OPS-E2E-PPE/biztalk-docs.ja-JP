---
title: "動的送信ポート ハンドラーは構成可能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5eb8f5ef-af95-4b2e-9a43-6f1240b25855
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11dffbe28d44d7665bc86ff0842c17ea01f7b3d3
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="dynamic-send-port-handler-is-configurable"></a>動的送信ポート ハンドラーは構成可能
アダプターの送信ハンドラーがの構成可能な動的送信ポートを作成するときに *すべて* アダプターをインストールします。 以下のシナリオについて考えてみます。  
  
 **シナリオ**  
  
 アプリケーションには 2 つの ESB 行程があります。 行程 1 では、動的送信ポートを使用してデータをファイル共有に送信します。 行程 2 では、動的送信ポートを使用して電子メールを送信します。 これまで、動的送信ポートはアダプターの既定のホストで実行されていました。 行程 1 は、分量が少なくてメッセージ サイズが大きいシナリオ向けに設計されています。 行程 2 は、分量が多くてメッセージ サイズが小さいシナリオを対象としています。 1 つのアダプターの既定のホストは 1 つだけなので、すべてのメッセージが同じホストを使用してルーティングされ、パフォーマンスを低下させています。  
  
 **変更**  
  
 動的送信ポートのパフォーマンスを向上させるために、任意のホストを使用するようにアダプターの送信ハンドラーを構成できます。 ESB シナリオでは、行程 1 で HostA を使用してデータをファイル共有に送信します。 行程 2 では、HostB ポートを使用して電子メールを送信します。  
  
## <a name="select-a-send-handler"></a>送信ハンドラーの選択  
 動的な一方向の送信ポートまたは動的な送信請求 - 応答の送信ポートを作成するとき、インストールされたすべてのアダプターについて送信ハンドラーを構成できます。 手順を実行します。  
  
1.  **BizTalk Server 管理コンソール**コンソールで、 **BizTalk グループ [*GroupName*]**、展開**アプリケーション**、順に展開送信ポートを格納するアプリケーション。  
  
2.  右クリック **送信ポート**, をクリックして **新規**, 、順にクリック **動的な一方向送信ポート** または **動的な送信請求-応答送信ポート**します。  
  
3.  **プロパティ**, 、クリックして **構成**します。  
  
     アダプターが既定の送信ハンドラーと共に一覧表示されます。 下矢印をクリックして別のホストを選択します。  
  
4.  クリックして **OK** 設定を保存します。  
  
5.  新しい動的送信ポートの参加を解除してから、もう一度参加させます。  
  
6.  元のホスト インスタンスを再起動します。  
  
7.  新しいホスト インスタンスを再起動します。  
  
 送信ポートのその他の構成オプションは次のとおりです。  
  
-   [詳細設定オプションの送信ポートのトランスポートを構成する方法](http://go.microsoft.com/fwlink/p/?LinkId=267697)  
  
-   [送信ポートに対してバックアップ トランスポートのオプションを構成する方法](http://go.microsoft.com/fwlink/p/?LinkId=267698)  
  
-   [送信ポートの送信マップを構成する方法](http://go.microsoft.com/fwlink/p/?LinkId=267699)  
  
-   [送信ポートのフィルターを構成する方法](http://go.microsoft.com/fwlink/p/?LinkId=267700)  
  
-   [送信ポートに証明書を割り当てる方法](http://go.microsoft.com/fwlink/p/?LinkId=267701)  
  
-   [送信ポートの追跡を構成する方法](http://go.microsoft.com/fwlink/p/?LinkId=267702)  
  
 さまざまなホストを微調整することができます。 次のリンクでは、パフォーマンスの最適化について説明しています。  
  
 [BizTalk Server の一般的な最適化](http://go.microsoft.com/fwlink/p/?LinkId=267703)  
  
 [BizTalk Server パフォーマンス設定を管理します。](http://go.microsoft.com/fwlink/p/?LinkId=267704)