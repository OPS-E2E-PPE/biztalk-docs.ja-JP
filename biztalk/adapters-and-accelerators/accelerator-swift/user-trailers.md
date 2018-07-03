---
title: ユーザー トレーラー |Microsoft Docs
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
ms.openlocfilehash: 10bc0d4d0fcdb36311e0590d9ae04239db168ed7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010219"
---
# <a name="user-trailers"></a>ユーザー トレーラー
ユーザー トレーラーから CHK トレーラー、を除き、省略可能で、存在する場合は、次の順序で発生します。  
  
|トレーラー コード|名前|  
|------------------|----------|  
|MAC|メッセージ認証コード|  
|PAC|独自の認証コード|  
|CHK|Checksum|  
|TNG|トレーニング|  
|PDE|可能な重複する出力|  
  
- **メッセージ認証コード (MAC) トレーラです。** により、受信側ユーザーを認証できます。 MAC のトレーラーには、認証の結果が続きます。 このトレーラーは、ほとんどのユーザーにメッセージ カテゴリ、FIN アプリケーション内で必須です。  
  
   FIN コピーのサービスを使用する場合 (存在する) 場合は、PAC トレーラーは MAC トレーラーに従います。 次のコードでは、MAC トレーラーの例を示します。  
  
  ```  
  {MAC:<authentication-result>}  
  where <authentication-result> = 8!h  
  ```  
  
- **独自の認証コード (PAC) のトレーラです。** PAC トレーラーは、二重認証オプションを使用する場合にのみ、FIN コピー サービス内で使用されます。 ブロック 5 の FIN ユーザーのユーザー メッセージには、存在する場合、直後に、MAC トレーラー PAC トレーラーが含まれます。 この結果が存在する場合に 115、フィールドの値は、メッセージのブロック 4 の抽出、フィールドに計算される、\<認証結果\>二重認証を使用したコピー サービスの MAC トレーラーの。  
  
   その結果、ブロックのインジケーター (CrLf-) が PAC の計算に含まれているし、フィールドは次のように定義されます。  
  
  - 最初の 4 つの文字は、CrLf は。  
  
  - フィールドと、区切り記号が存在する場合は、32 a は、:、20: これにします。  
  
  - すべてのサブフィールドとその区切り記号は存在します。  
  
    次のコードでは、PAC トレーラーの形式の例を示します。  
  
  ```  
  {PAC:[<authentication-result>]}  
  where <authentication-result> is mandatory on input messages only and  
  <authentication-result> = 8!h  
  ```  
  
- **(チェックサム) から CHK トレーラー (必須のすべての FIN メッセージ)**  
  
   CHK トレーラーは FIN メッセージをすべての必須であり、受信者のアドレスに基づいて計算されます (9 番目の文字で 12 文字に置き換え*X*さらに、テキスト ブロック)。 このトレーラーは、システムおよびシステムの動作不良または検出の伝送エラーによりメッセージが破損していないことを確認するために CBT を許可します。  
  
   次のコードでは、から CHK トレーラーの形式の例を示します。  
  
  ```  
  {CHK:<checksum-result>}  
  where <checksum-result> = 12!h  
  ```  
  
## <a name="see-also"></a>参照  
 [スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)