---
title: その他のトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: eb284d6d869834e3e6d148e2582043e3789f43ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377188"
---
# <a name="miscellaneous-troubleshooting"></a>その他のトラブルシューティング
## <a name="leading-zeroes-validation-is-not-performed-for-fields-that-use-the-checkleadingzeroesinelement-method-to-validate-a-field-in-the-message-validation-policy"></a>先頭のゼロ CheckLeadingZeroesInElement メソッドを使用して、メッセージ検証ポリシー内のフィールドを検証するフィールドの検証が実行されません。  
  
### <a name="symptom"></a>現象  
 フィールドには、先頭のゼロは許可されていないと、検証ポリシーには、この検証を実行するフィールドのルールが含まれていますが、フィールドに先行ゼロをメッセージが送信される場合は、BRE の検証のエラーは返されません。  
  
### <a name="possible-cause"></a>考えられる原因  
 **CheckLeadingZeroInElement**メソッドが、メッセージの種類の検証ポリシーでビジネス ルールに含まれています。 このメソッドが非推奨とされます。 関数呼び出しでは、検証、関数呼び出しで指定された要素が先頭にゼロがある場合のエラーを引き起こします。 ただし、フィールドに先行ゼロがある場合でも、このメソッドは検証に失敗を発生できません。  
  
### <a name="solution"></a>ソリューション  
 実装する必要がある先頭のゼロを確認する場合、 **CheckLeadingZero**メソッドの代わりに、 **CheckLeadingZeroInElement**メソッド。 **CheckLeadingZero**関数への文字列入力に先行ゼロがある場合、検証エラーが発生します。  
  
 実装する、 **CheckLeadingZero**メソッドを呼び出すカスタム メソッドを作成する必要があります、 **CheckLeadingZero**ユーザー定義関数内からメソッドを文字列として値を提供し、先頭のゼロを検証します。 これは、ため**CheckLeadingZero**エラーを記録しませんが、代わりに単に False を返します、ブール値、入力文字列が有効な SWIFT 数値フィールドではない場合、または文字列入力に先行ゼロがある場合。 それ以外の場合、True を返します。 カスタム メソッドはエラーを適宜記録し、できます。  
  
## <a name="an-error-is-returned-by-the-message-validation-policy-if-the-swift-number-field-has-a-leading-zero"></a>SWIFT 番号フィールドに、先行ゼロがある場合、メッセージの検証ポリシーによってエラーが返されます  
  
### <a name="symptom"></a>現象  
 メッセージが送信される場合に、フィールドに先行ゼロ場合でも、先行するフィールドのゼロが許可されている、BRE の検証エラーが返されます。  
  
### <a name="possible-cause"></a>考えられる原因  
 これは、次のメソッドのいずれかがにとっては、ルールのアクションの一部では、通常のルールで SWIFT 番号フィールドの検証に使用される場合に発生します。 これは、量、速度、価格、または数量フィールドで発生します。  
  
-   **CheckCurrencyAmount**  
  
-   **CheckValidAmount**  
  
-   **CheckValidCurrencyAndPriceCode**  
  
-   **CheckValidSignCurrencyAmount**  
  
-   **CheckValidSignDateCurrencyAmount**  
  
-   **CheckValidSignRate**  
  
-   **IsValidTransactionDetailsCurrencyAmount**  
  
### <a name="solution"></a>ソリューション  
 場合、上記のリスト内のメソッドのいずれか以外の**CheckValidSignRate**、検証ポリシーでは、先行するゼロ」の説明に従って有効にするルールで使用される、[量フィールド検証で先行ゼロをサポートしている](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md).  
  
 場合、 **CheckValidSignRate**メソッドがこのエラーを返したルールで使用される、先頭のゼロをサポートする唯一の方法は検証ポリシーからこのルールを削除します。 これを実現する次の手順に従います。  
  
1.  ビジネス ルール作成ツールを右クリックし、**バージョン**ノードを展開したポリシーを使用して規則を含む、 **CheckValidSignRate**メソッド。 クリックして**展開解除**します。  
  
2.  右クリックし、**バージョン**同じポリシー、およびクリック ノード**コピー**します。  
  
3.  右クリックし、 **Validation_Policy**同じポリシー、およびクリック ノード**貼り付け**します。  
  
4.  新しい保存されていないバージョンのポリシーを展開します。 持つルールを右クリックし、 **CheckValidSignRate**メソッドの呼び出しをクリック**削除**します。  
  
5.  ポリシーが保存されていない新しい右クリック**バージョン**ノード、およびクリック**保存**。 同じノードを右クリックし、をクリックし、**発行**します。 同じノードを右クリックし、をクリックし、**デプロイ**します。  
  
## <a name="a4swift-database-requires-archiving"></a>A4SWIFT データベースのアーカイブが必要です。  
  
### <a name="symptom"></a>現象  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースが大きく増加しています。  
  
### <a name="possible-cause"></a>考えられる原因  
 履歴テーブルで、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースが自動的にアーカイブしていません。 このテーブルには、メッセージの修復と新しい送信、タスクと、オーケストレーション プロセスに関するデータを実行したユーザーなどに関するデータが格納されます。 このテーブルは、メッセージの修復と新しい送信の操作を実行するようを拡張し続けます。  
  
### <a name="solution"></a>ソリューション  
 増加を制限する、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースで、標準のアーカイブのプロシージャを使用して、履歴テーブルからデータを定期的にアーカイブします。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティング: 問題と解決方法](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)