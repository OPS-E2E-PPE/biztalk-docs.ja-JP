---
title: ユーザーのトレーラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: 340d9fc8-467b-4cba-b69f-eb761767deaa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff907e262088acd188028282fe2e03441071358a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961984"
---
# <a name="user-trailers"></a>ユーザーのトレーラー
ユーザーのトレーラー、CHK トレーラーを除くはオプションであり、存在する場合は、次の順序で発生します。  
  
|トレーラー コード|名前|  
|------------------|----------|  
|MAC|メッセージ認証コード|  
|PAC|独自の認証コード|  
|CHK|Checksum|  
|TNG|トレーニング|  
|PDE|考えられる重複する出力|  
  
-   **メッセージ認証コード (MAC) のトレーラです。** により、受信側ユーザーを認証できます。 MAC トレーラーには、認証の結果が続きます。 このトレーラーは、ほとんどのユーザーにメッセージ カテゴリ、FIN アプリケーション内で必須です。  
  
     FIN コピー サービスを使用すると、PAC トレーラー (存在する場合) には、MAC トレーラーが次に示します。 次のコードは、MAC トレーラーの例です。  
  
    ```  
    {MAC:<authentication-result>}  
    where <authentication-result> = 8!h  
    ```  
  
-   **独自の認証コード (PAC を) トレーラです。** 二重認証オプションを使用する場合にのみ、PAC トレーラーは FIN コピー サービス内で使用されます。 ブロック 5 の FIN ユーザー-ユーザーへのメッセージには、存在する場合、MAC トレーラーの直後に、PAC トレーラーが含まれます。 この結果が計算される 115、フィールドの値、メッセージのブロック 4 のフィールドの抽出に存在する場合、および\<認証結果\>コピー サービスの認証では二重の MAC トレーラーのです。  
  
     その結果、PAC の計算でブロックのインジケーター (CrLf-) が含まれているし、フィールドは次のように定義されます。  
  
    -   最初の 4 つの文字は、CrLf:  
  
    -   フィールドと、区切り記号がある、32 a は、:、20: のようにします。  
  
    -   すべてのサブフィールドとその区切り記号は存在します。  
  
     次のコードでは、PAC トレーラー形式の例を示します。  
  
    ```  
    {PAC:[<authentication-result>]}  
    where <authentication-result> is mandatory on input messages only and  
    <authentication-result> = 8!h  
    ```  
  
-   **CHK (チェックサム) トレーラー (必須のすべての FIN メッセージ)**  
  
     CHK トレーラーは FIN メッセージをすべての必須であり、受信者のアドレスに基づいて計算されます (9 番目の文字で 12 文字で置換*X*さらに、テキスト ブロック) します。 このトレーラーは、システムおよびシステムが誤動作または検出されていない転送エラーのためのメッセージが破損していないことを確認する CBT を許可します。  
  
     次のコードでは、CHK トレーラー形式の例を示します。  
  
    ```  
    {CHK:<checksum-result>}  
    where <checksum-result> = 12!h  
    ```  
  
## <a name="see-also"></a>参照  
 [スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)