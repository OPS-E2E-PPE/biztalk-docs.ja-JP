---
title: EDIFACT CONTRL 確認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 95e1c244-d700-48d3-9416-032ead6d4d6d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7808b02e5aebcf9f03e06a13ebbbcff8b1f43b0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350126"
---
# <a name="edifact-contrl-acknowledgment"></a>EDIFACT CONTRL 確認
CONTRL 受信確認 (ACK) は、EDIFACT でエンコードされたメッセージの技術と機能の両方の受信確認として機能します。 技術確認として CONTRL メッセージは、インターチェンジの受信を示します。 機能確認として CONTRL メッセージの受理または拒否された受信したインターチェンジ、グループ、またはメッセージ、エラーまたはサポートされていない機能の一覧を示します。  
  
 機能確認をとして CONTRL メッセージの全文 機能確認のセクションでは、技術確認で再利用します。 送信元パーティまたはグローバル プロパティでは、技術と機能の両方の Ack をパーティのプロパティで選択した、BizTalk Server は 2 つの CONTRL メッセージを生成: 技術 CONTRL 確認と機能 CONTRL 確認  
  
 CONTRL 確認は、efact _ に準拠している\<バージョン番号\>>_contrl.xsd スキーマ。  
  
## <a name="technical-acknowledgement"></a>技術確認  
 技術確認を意味するインターチェンジの受信者。  
  
-   対象のインターチェンジが受信します。  
  
-   UCI レポート セグメントにコピーされたデータ要素が構文的に正しいことを確認するためにチェックされている件名のインターチェンジの各部を確認します。  
  
-   受信確認の送信側または件名のインターチェンジの他の部分の却下を通知する責任を承諾しました  
  
-   送信者が通知されますのでことを確認するには妥当な予防措置を実行しています。  
  
## <a name="functional-acknowledgement"></a>機能確認  
 意味する機能確認インターチェンジの受信者。  
  
- 受信したインターチェンジの受信確認; の参照のレベル (s)  
  
- さらには、インターチェンジの処理を確認した参照レベルで致命的な構文エラーがないことをチェックしました。  
  
- オンにする (エラーが報告されていない) 場合にセグメントが意味的サービスの確認部分すべてが修正;  
  
- 受信確認を送った参照レベル サービス セグメントの要求されたアクションに準拠します。  
  
- 構文またはセマンティック エラー、前述のようが後で検出された場合、一部または関連の部分では、CONTRL メッセージの送信を処理できません何らかの理由により、一部がよりも、他の方法で送信者を通知する責任を承諾しました送信された CONTRL メッセージの受信確認を受け取りました  
  
- このようなエラーが検出されると、送信者に通知することを確認するには妥当な予防措置を実行しているとします。  
  
  意味する拒否インターチェンジの受信者。  
  
- 対象のインターチェンジ、または CONTRL メッセージに示されている上の理由から、関連する部分を確認することはできません。  
  
- 件名のインターチェンジの拒否された部分に含まれるビジネス情報に、さらにアクションを実行しません。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [技術確認としての EDIFACT CONTRL メッセージ](../core/edifact-contrl-message-as-technical-acknowledgment.md)  
  
-   [機能確認としての EDIFACT CONTRL メッセージ](../core/edifact-contrl-message-as-functional-acknowledgment.md)  
  
## <a name="see-also"></a>参照  
 [EDI 受信確認構造](../core/edi-acknowledgment-structure.md)