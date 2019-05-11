---
title: 修復し、メッセージを再 |Microsoft Docs
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
ms.openlocfilehash: c29e39eaff4cdc1513fea4dd434fda9348d85fcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301733"
---
# <a name="repairing-and-resubmitting-a-message"></a>修復し、メッセージを再送信
修復、失敗したメッセージを再送信するには、ESB 管理ポータルのエラー ページを使用します。  
  
### <a name="to-repair-and-resubmit-a-message-for-processing"></a>修復処理のためのメッセージを再送信するには  
  
1.  目的のエラー メッセージを検索、[ポータル エラー ページ](../esb-toolkit/portal-faults-page.md)ESB 管理ポータルのページ。 エラー ページのフィルター処理機能を使用して、特定のメッセージの検索します。 空のままに、コントロールのいずれかをすべてのメッセージを取得します。 非常に大きな障害のデータベースでフィルター処理が適切な結果を表示するのに数秒間かかる場合がありますに注意してください。 図 1 は、エラー ページを示しています。  
  
     ![FaultsPage](../esb-toolkit/media/faultspage.gif "FaultsPage")  
  
     **図 1**  
  
     **ESB 管理ポータルの [エラー] ページ**  
  
2.  任意の場所を開く必要なエラー メッセージの行をクリックして、[ポータル エラー メッセージ ビューアー](../esb-toolkit/portal-fault-message-viewer.md)ページ[エラーの詳細ビュー](../esb-toolkit/fault-details-view.md)します。  
  
3.  エラー メッセージ内のメッセージの一覧にエラーの詳細ビューの一番下までスクロールします。 図 2 に示します、**メッセージ**フォールト ビューアー ページのセクション。  
  
     ![メッセージ セクション](../esb-toolkit/media/ch8-messagessection.gif "Ch8 MessagesSection")  
  
     **図 2**  
  
     **ESB 管理ポータルの [フォールト ビューアー] ページの [メッセージ] セクション**  
  
4.  再送信するメッセージのメッセージ id をクリックします。 内のメッセージが開きます[メッセージの詳細ビュー](../esb-toolkit/message-details-view.md)図 3 に示すように、個々 のメッセージとメッセージの内容の詳細を表示します。  
  
     ![メッセージ ビューアー](../esb-toolkit/media/ch8-messageviewer.gif "Ch8 MessageViewer")  
  
     **図 3**  
  
     **ESB 管理ポータルの [メッセージ ビューアー] ページ**  
  
5.  をクリックして、**編集**に切り替える編集モード、および必要に応じて、メッセージの内容を編集し、メッセージの内容を含むテキスト ボックスの下のリンク。 たとえば、メッセージ内に含まれるサービス メソッドの呼び出しのパラメーターを変更する必要があります。 再送信されたときに、メッセージの拒否を防ぐためにネイティブなドキュメント スタイル (XML、フラット ファイル形式など) に従う必要がありますに注意してください。 図 4 に示します、**メッセージの詳細**メッセージ エディター ページのセクション。  
  
     ![メッセージの詳細](../esb-toolkit/media/ch8-messagedetails.gif "Ch8 MessageDetails")  
  
     **図 4**  
  
     **ESB 管理ポータルの [メッセージ ビューアー] ページの [メッセージの詳細] セクション**  
  
6.  メッセージを編集した後に、メッセージのテキスト ボックスの下のドロップダウン リストで再送信の場所を選択します。 この一覧は、使用可能なエンドポイントの動的に取得した一覧を示します。 再送信エンドポイントとして構成されたエンドポイントを選択する必要があります。 次のエンドポイントは再送信に適しています。  
  
    -   **WCF 入口**します。 このエンドポイントは、ランプの ESB 行程 Services の WCF では XML ファイルでのみ使用できます。 ポータルの Web.config ファイルでは、この入り口の URL を定義します。  
  
    -   **SOAP 入口**します。 このエンドポイントは、ランプの ESB 行程サービス ASMX では XML ファイルでのみ使用できます。 ポータルの Web.config ファイルでは、この入り口の URL を定義します。  
  
    -   **いずれかの受信場所の BizTalk HTTP アダプターを使用して**します。 このオプションは XML ファイルとフラット ファイルの使用です。  
  
7.  をクリックして、**再送信**メッセージ再送信へのリンク。 示すメッセージ、**再送信の状態**メッセージ コンテンツのテキスト ボックスの下に表示されます。  
  
8.  必要な場合、開く、[監査ログ ページ](../esb-toolkit/audit-log-page.md)から、**管理者** タブを図 5 に示すように、メッセージの再送信を確認します。  
  
     ![AuditLog ページの小さなビュー](../esb-toolkit/media/ch8-auditlogpagesmallview.gif "Ch8 AuditLogPageSmallView")  
  
     **図 5**  
  
     **ESB 管理ポータルの監査ログ ページ**