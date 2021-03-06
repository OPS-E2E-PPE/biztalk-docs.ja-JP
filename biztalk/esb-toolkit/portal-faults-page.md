---
title: ポータル エラー ページ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b11e3492-da1a-43f3-acf8-3775b5cbc2c5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54a0f0d2fb165a550e3882d81409d893d34b44e2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295156"
---
# <a name="portal-faults-page"></a>ポータル エラー ページ
図 1 は、エラー ページを示します。 このページには、それぞれの障害の主要なプロパティが表示されます。 および、並べ替えおよびフィルター処理のエラーの種類や時間などの条件の範囲にエラーの詳細な分析をサポートする機能を提供します。 各エラーへのリンクを使用すると、エラー メッセージのビューアーで詳細を表示できます。  
  
 ![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")  
  
 **図 1**  
  
 **ESB 管理ポータルの [エラー] ページ**  
  
 次の一覧では、ESB 管理ポータル エラー ページの機能を使用する方法について説明します。  
  
-   ページに表示されるエラーの一覧をフィルター処理するには、エラーの一覧の上のテキスト ボックス、ドロップダウン リストを使用します。 次のように表示される行をフィルター処理できます。  
  
    -   いずれかでインストール済みの BizTalk アプリケーションの選択、**アプリケーション**ドロップダウン リスト。  
  
    -   ある障害の発生を選択して、期間を指定**時間、日、週、月、四半期、年、** または**すべて**で、**最後内のレコードを取得**ドロップダウン リスト。  
  
    -   ページで表示する行の数を指定、 **1 ページあたりのレコード**ドロップダウン リスト。  
  
    -   エラー コード番号を入力、**エラーコード**テキスト ボックス。  
  
    -   障害カテゴリ名の一部またはすべてを入力、**障害カテゴリ**テキスト ボックス。  
  
    -   エラーの種類のテキストの一部またはすべてを入力、**エラーの種類**テキスト ボックス。  
  
    -   最小および最大の障害の重大度の値を入力 (など**警告、エラー、重大、** または**重大**) で、 **Min のエラーの重大度**と**最大の障害重大度**テキスト ボックス。  
  
-   これらのコントロールの 1 つ以上の値を指定した後にをクリックして、**フィルターの適用**指定されたすべての条件を適用するボタンをクリックします。  
  
-   その列の内容の順序でフォールト メッセージ行を表示する列見出しをクリックし、逆の順序で一覧を表示し、もう一度クリックします。  
  
-   一覧に表示されるエラーの詳細を表示または編集が含まれているメッセージを再送信をクリックします任意の場所で開くには、そのエラーの行で、[ポータル エラー メッセージ ビューアー](../esb-toolkit/portal-fault-message-viewer.md)します。