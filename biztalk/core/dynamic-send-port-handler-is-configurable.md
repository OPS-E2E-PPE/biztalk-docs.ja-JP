---
title: 動的送信ポート ハンドラーは構成可能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eb8f5ef-af95-4b2e-9a43-6f1240b25855
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21f4985b3e22bd2095e66c240d6c614e1a88c45c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389268"
---
# <a name="dynamic-send-port-handler-is-configurable"></a>動的送信ポート ハンドラーは構成可能です。
動的送信ポートを作成するときに、インストールされている*すべて*のアダプターについて、アダプターの送信ハンドラーを構成できます。 次のシナリオを考えてみましょう。  
  
 **Scenario**  
  
 アプリケーションには、2 つの ESB 行程があります。 行程 1 では、動的送信ポートを使用して、ファイル共有にデータを送信します。 行程 2 では、動的送信ポートを使用して、電子メールを送信します。 以前は、動的送信ポートは、アダプターの既定のホストで実行します。 行程 1 は、少量の大きなメッセージ サイズのシナリオを対象に設計されています。 行程 2 は、大量の小さなメッセージ サイズのシナリオを対象とします。 アダプターの既定のホストを 1 つだけなので、パフォーマンスが低下、同じホストを使用してすべてのメッセージがルーティングされます。  
  
 **変更**  
  
 動的送信ポートのパフォーマンスを向上させるのには、アダプターの送信ハンドラーは任意のホストを使用する構成できます。 ESB シナリオでは、行程 1 は、ファイル共有にデータを送信するのに HostA を使用します。 行程 2 では、HostB ポートを使用して、電子メールを送信します。  
  
## <a name="select-a-send-handler"></a>送信ハンドラーを選択します。  
 動的な一方向送信ポートまたは動的な送信請求-応答送信ポートを作成する場合、送信ハンドラーがすべてインストールされているアダプターの構成可能です。 手順:  
  
1. **BizTalk Server 管理**コンソールで、 **BizTalk グループ [*GroupName*]**、展開**アプリケーション**、順に展開送信ポートを格納するアプリケーションです。  
  
2. 右クリック**送信ポート**、 をクリックして**新規**、 をクリックし、**動的な一方向送信ポート**または**動的な送信請求-応答送信ポート**します。  
  
3. **プロパティ**、 をクリックして**構成**します。  
  
    アダプターは、既定の送信ハンドラーと共に一覧表示されます。 別のホストを選択して下矢印をクリックします。  
  
4. クリックして**OK**設定を保存します。  
  
5. 参加を解除し、新しい動的送信ポートを登録します。  
  
6. 元のホスト インスタンスを再起動します。  
  
7. 新しいホスト インスタンスを再起動します。  
  
   送信ポートのその他の構成オプションは次のとおりです。  
  
- [送信ポートに対してトランスポートの詳細オプションを構成する方法](http://go.microsoft.com/fwlink/p/?LinkId=267697)  
  
- [送信ポートに対してバックアップ トランスポートのオプションを構成する方法](http://go.microsoft.com/fwlink/p/?LinkId=267698)  
  
- [送信ポートの送信マップを構成する方法](http://go.microsoft.com/fwlink/p/?LinkId=267699)  
  
- [送信ポートのフィルターを構成する方法](http://go.microsoft.com/fwlink/p/?LinkId=267700)  
  
- [送信ポートに証明書を割り当てる方法](http://go.microsoft.com/fwlink/p/?LinkId=267701)  
  
- [送信ポートの追跡を構成する方法](http://go.microsoft.com/fwlink/p/?LinkId=267702)  
  
  さまざまなホストを微調整できます。 次のリンクでは、パフォーマンスの最適化について説明します。  
  
  [BizTalk Server の一般的な最適化](http://go.microsoft.com/fwlink/p/?LinkId=267703)  
  
  [BizTalk Server パフォーマンス設定の管理](http://go.microsoft.com/fwlink/p/?LinkId=267704)