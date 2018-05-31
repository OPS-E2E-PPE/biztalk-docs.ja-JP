---
title: 修復と再送信するメッセージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccd720b4-44a2-4c44-bf6e-8cf5e9ded1aa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e524ffca1b79032dce55f74e195032d14ec1bf9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295058"
---
# <a name="repairing-and-resubmitting-a-message"></a>修復と再送信するメッセージ
修復する失敗したメッセージを再送信するには、ESB の管理ポータルの [エラー] ページを使用します。  
  
### <a name="to-repair-and-resubmit-a-message-for-processing"></a>修復処理のためのメッセージを再送信するには  
  
1.  必要なエラー メッセージを確認、[ポータル エラー ページ](../esb-toolkit/portal-faults-page.md)ESB 管理ポータルのページです。 エラー ページでフィルター処理機能を使用して、特定のメッセージを検索します。 空のままにコントロールのいずれかのすべてのメッセージを取得します。 非常に大きな障害データベースでフィルター処理が適切な結果を表示するのに数秒間かかる場合がありますに注意してください。 図 1 は、エラー ページを示しています。  
  
     ![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")  
  
     **図 1**  
  
     **ESB の管理ポータルの [エラー] ページ**  
  
2.  任意の場所を開くには必要なエラー メッセージの行をクリックして、[ポータル フォールト メッセージ ビューアー](../esb-toolkit/portal-fault-message-viewer.md)ページ[エラーの詳細ビュー](../esb-toolkit/fault-details-view.md)です。  
  
3.  エラー メッセージ内のメッセージの一覧にエラーの詳細ビューの一番下までスクロールします。 図 2 を示しています、**メッセージ**フォールト ビューアー ページのセクションです。  
  
     ![メッセージのセクション](../esb-toolkit/media/ch8-messagessection.gif "Ch8 MessagesSection")  
  
     **図 2**  
  
     **ESB の管理ポータルの [フォールト ビューアー] ページの Messages セクション**  
  
4.  再送信するメッセージのメッセージ id をクリックします。 内のメッセージが開きます[メッセージの詳細ビュー](../esb-toolkit/message-details-view.md)図 3 に示すように個々 のメッセージとメッセージの内容の詳細が示されます。  
  
     ![メッセージのビューアー](../esb-toolkit/media/ch8-messageviewer.gif "Ch8 MessageViewer")  
  
     **図 3**  
  
     **ESB の管理ポータルの [メッセージ ビューアー] ページ**  
  
5.  クリックして、**編集**編集モード、および必要に応じて、メッセージの内容を編集に切り替えるには、メッセージ コンテンツを含むテキスト ボックスの下のリンク。 たとえば、メッセージ内に含まれるサービスのメソッドの呼び出しのパラメーターを変更する必要があります。 再送信されたときに、メッセージの拒否を防ぐために (XML またはフラット ファイル形式) などのネイティブのドキュメントのスタイルに従う必要がありますに注意してください。 図 4 を示しています、**メッセージの詳細**メッセージ エディター ページのセクションでします。  
  
     ![メッセージの詳細](../esb-toolkit/media/ch8-messagedetails.gif "Ch8 MessageDetails")  
  
     **図 4**  
  
     **ESB の管理ポータルの [メッセージ ビューアー] ページの [メッセージの詳細] セクション**  
  
6.  メッセージを編集した後に、メッセージのテキスト ボックスの下のドロップダウン リストで再送信場所を選択します。 この一覧は、使用可能なエンドポイントの動的に取得した一覧を示します。 再送信エンドポイントとして構成されたエンドポイントを選択する必要があります。 次のエンドポイントの再送信に適したのとおりです。  
  
    -   **WCF 入り口**です。 このエンドポイントの ESB 行程 Services WCF 入り口、XML ファイルに対してのみ使用できます。 ポータルの Web.config ファイルでは、この入り口の URL を定義します。  
  
    -   **SOAP 入り口**です。 このエンドポイントの ESB 行程サービス ASMX 入り口、XML ファイルに対してのみ使用できます。 ポータルの Web.config ファイルでは、この入り口の URL を定義します。  
  
    -   **いずれかの受信場所の BizTalk HTTP アダプターを使用して**です。 このオプションは XML ファイルとフラット ファイルの使用です。  
  
7.  クリックして、**を再送信**メッセージ再送信へのリンク。 示すメッセージ、**再送信状態**メッセージ コンテンツのテキスト ボックスの下に表示されます。  
  
8.  必要な場合、開く、[監査ログ ページ](../esb-toolkit/audit-log-page.md)から、**管理者**図 5 に示すように、メッセージの再送信を確認します。  
  
     ![AuditLog ページの小さなビュー](../esb-toolkit/media/ch8-auditlogpagesmallview.gif "Ch8 AuditLogPageSmallView")  
  
     **図 5**  
  
     **ESB の管理ポータルの [監査ログ] ページ**