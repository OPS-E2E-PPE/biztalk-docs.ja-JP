---
title: "EDIFACT CONTRL 確認 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95e1c244-d700-48d3-9416-032ead6d4d6d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baaca02ac076c79be004ed7b3d2c0f4fffce6ff9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edifact-contrl-acknowledgment"></a>EDIFACT CONTRL 確認
CONTRL 確認 (ACK) は、EDIFACT エンコード メッセージの技術確認および機能確認として機能します。 技術確認としての CONTRL メッセージは、インターチェンジの受信を示します。 機能確認としての CONTRL メッセージは、エラーまたはサポートされていない機能の一覧を含んでおり、受信したインターチェンジ、グループ、またはメッセージの受理または拒否を示します。  
  
 CONTRL メッセージの全文は、機能確認として機能します。 機能確認の各セクションは、技術確認のために再使用されます。 送信元パーティまたはグローバル プロパティでは、技術と機能の両方の Ack をパーティのプロパティで選択した、BizTalk Server は次の 2 つの CONTRL メッセージを生成: 技術 CONTRL 確認と機能 CONTRL 確認です。  
  
 CONTRL 確認は、efact _ に準拠している\<バージョン番号 > >_contrl.xsd スキーマです。  
  
## <a name="technical-acknowledgement"></a>技術確認  
 技術確認は、インターチェンジの受信に関する次の内容を意味します。  
  
-   件名のインターチェンジを受信したこと。  
  
-   UCI レポート セグメントにコピーされたデータ要素の構文が正しいかどうかがチェックされている件名のインターチェンジの各部を確認したこと。  
  
-   件名のインターチェンジの他の部分を受理または拒否したことを送信者に通知する責任を受け入れたこと。  
  
-   送信者に確実に通知するための適切な対策を講じていること。  
  
## <a name="functional-acknowledgement"></a>機能確認  
 機能確認は、インターチェンジの受信に関する次の内容を意味します。  
  
-   確認したインターチェンジの参照レベルを受信していること。  
  
-   確認した参照レベルに、インターチェンジの後続処理を妨げるような致命的な構文エラーがないことをチェックしたこと。  
  
-   サービス セグメントの確認部分すべてが意味的に正しい (エラーが報告されていない) ことをチェックしたこと。  
  
-   サービス セグメントの確認した参照レベル内で要求されたアクションに準拠すること。  
  
-   前述の構文的なエラーまたはセマンティック エラーが関連部分で後から検出された場合、または、送信された CONTRL メッセージ内でその部分が確認された後でなんらかの他の理由によりこの部分の処理ができない場合に、CONTRL メッセージの送信以外の方法で送信者に通知する責任を受け入れたこと。  
  
-   このようなエラーを検出し、送信者に通知するための適切な対策を講じていること。  
  
 拒否は、インターチェンジの受信に関する次の内容を意味します。  
  
-   CONTRL メッセージに示されている理由により、件名のインターチェンジまたはその関連部分を確認できないこと。  
  
-   件名のインターチェンジの拒否された部分に含まれているビジネス情報に対し、それ以上のアクションを行わないこと。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [技術確認としての EDIFACT CONTRL メッセージ](../core/edifact-contrl-message-as-technical-acknowledgment.md)  
  
-   [機能確認としての EDIFACT CONTRL メッセージ](../core/edifact-contrl-message-as-functional-acknowledgment.md)  
  
## <a name="see-also"></a>参照  
 [EDI 受信確認構造](../core/edi-acknowledgment-structure.md)