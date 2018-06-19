---
title: その他のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 6ebc1867-b5d3-46de-b3bd-69e570ed2b2c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765b32895fa76c0c77b740b76e2e6a03f0571351
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211178"
---
# <a name="miscellaneous-troubleshooting"></a>その他のトラブルシューティング
## <a name="leading-zeroes-validation-is-not-performed-for-fields-that-use-the-checkleadingzeroesinelement-method-to-validate-a-field-in-the-message-validation-policy"></a>先頭のゼロ CheckLeadingZeroesInElement メソッドを使用して、メッセージ検証ポリシー内のフィールドを検証するフィールドの検証が行われません。  
  
### <a name="symptom"></a>現象  
 フィールドには、先頭のゼロは許可されていないと、検証ポリシーには、この検証を実行するフィールドの規則が含まれています。 場合でも、フィールドに伴い、先行ゼロでメッセージが送信された場合、BRE の妥当性確認エラーは返されません。  
  
### <a name="possible-cause"></a>考えられる原因  
 **CheckLeadingZeroInElement**メソッドは、メッセージの種類の検証ポリシーでビジネス ルールに含まれています。 このメソッドは推奨されません。 関数呼び出しの目的は、検証、関数呼び出しで指定された要素が先頭にゼロがある場合のエラーを引き起こすを開始します。 ただし、フィールドに、先行ゼロがある場合でも、このメソッドは検証に失敗を発生しません。  
  
### <a name="solution"></a>解決方法  
 実装する必要がありますを伴い、先行ゼロをチェックする場合、 **CheckLeadingZero**メソッドの代わりに、 **CheckLeadingZeroInElement**メソッドです。 **CheckLeadingZero**関数への入力を文字列に先行ゼロがある場合、検証エラーが発生します。  
  
 実装する、 **CheckLeadingZero**メソッドを呼び出すカスタム メソッドを作成する必要があります、 **CheckLeadingZero**ユーザー定義関数内からメソッドを文字列としての値を提供して先頭のゼロを検証します。 これは、ため**CheckLeadingZero** 、エラー ログに記録しませんが、代わりに単に返すブール値 False、入力文字列が有効な SWIFT 数値フィールドではない場合、または入力文字列に先行ゼロがある場合。 それ以外の場合、True を返します。 カスタム メソッドはそれに応じてエラーをログインし、実行できます。  
  
## <a name="an-error-is-returned-by-the-message-validation-policy-if-the-swift-number-field-has-a-leading-zero"></a>SWIFT 番号フィールドに、先行ゼロがある場合、メッセージ検証ポリシーによって、エラーが返されます  
  
### <a name="symptom"></a>現象  
 メッセージが送信されるフィールドに先行ゼロを場合でも、先頭のゼロがフィールドで許可されている場合は、BRE の検証エラーが返されます。  
  
### <a name="possible-cause"></a>考えられる原因  
 これは、次のいずれかの使用に関する、通常、ルールのアクションの一部のルールに SWIFT 番号フィールドを検証する場合に発生します。 これは、量やレート、価格、数量フィールドで発生する可能性があります。  
  
-   **CheckCurrencyAmount**  
  
-   **CheckValidAmount**  
  
-   **CheckValidCurrencyAndPriceCode**  
  
-   **CheckValidSignCurrencyAmount**  
  
-   **CheckValidSignDateCurrencyAmount**  
  
-   **CheckValidSignRate**  
  
-   **IsValidTransactionDetailsCurrencyAmount**  
  
### <a name="solution"></a>解決方法  
 場合は、上記のリスト内のいずれかの除く**CheckValidSignRate**、ルールの検証ポリシーを有効にする」の説明に従って、先行ゼロで使用される[量フィールドの検証時に先行ゼロをサポートする](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md).  
  
 場合、 **CheckValidSignRate**メソッドがこのエラーを返したルールで使用される、伴い、先行ゼロをサポートする唯一の方法は、検証ポリシーからこのルールを削除します。 これを実現するには、次の手順に従います。  
  
1.  ビジネス ルール作成ツールで右クリックし、**バージョン**ノードを展開したポリシーを使用してルールを含む、 **CheckValidSignRate**メソッドです。 をクリックして**展開解除**です。  
  
2.  右クリックし、**バージョン**ノードをクリックして同じポリシー、**コピー**です。  
  
3.  右クリックし、 **Validation_Policy**ノードをクリックして同じポリシー、**貼り付け**です。  
  
4.  新しい保存されていないバージョンのポリシーを展開します。 持つルールを右クリックし、 **CheckValidSignRate**クリックしてメソッドを呼び出す**削除**です。  
  
5.  ポリシー未保存の新しい右クリックして**バージョン**ノードをクリックして**保存**です。 同じノードを右クリックし、をクリックして**発行**です。 同じノードを右クリックし、をクリックして**展開**です。  
  
## <a name="a4swift-database-requires-archiving"></a>A4SWIFT データベースでは、アーカイブが必要です。  
  
### <a name="symptom"></a>現象  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースが大きくなりすぎます。  
  
### <a name="possible-cause"></a>考えられる原因  
 履歴テーブルで、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースが自動的にアーカイブされていません。 次の表は、メッセージの修復と新しい送信、タスクと、オーケストレーション プロセスに関するデータを実行したユーザーなどに関するデータを格納します。 次の表は、メッセージの修復や新しい送信操作を行うにつれて続行されます。  
  
### <a name="solution"></a>解決方法  
 増大を制限、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースを定期的にアーカイブのプロシージャの標準を使用して、履歴テーブルからデータをアーカイブします。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティング: 問題と解決策](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)