---
title: EDI ヘッダーとトレーラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf1dae3-9570-413d-a85d-94dcbb561906
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77f30def9b680c04fd0078e253dcb4f1049f9d56
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530837"
---
# <a name="edi-headers-and-trailers"></a>EDI ヘッダーとトレーラー
EDI インターチェンジの部分は、ヘッダーとトレーラー、X12 または EDIFACT 標準に準拠する必要があるによって区切られます。 インターチェンジ制御ヘッダーとトレーラーは 1 回だけ発生します。機能グループおよびトランザクション セットのヘッダーとトレーラーが繰り返されるは、トランザクション セットとグループは、インターチェンジ内でバッチ処理される場合。 一連のヘッダーとトレーラーが含まれているコンテンツに関する情報を含むデータ要素の各ヘッダーとトレーラーで構成されます。  
  
 ヘッダーとトレーラーは X12 と EDIFACT の両方に似ています。 主な違いは、edifact の場合、インターチェンジで使用される区切り記号を定義する UNA サービス文字列通知ヘッダーです。 X12 エンコードでは、区切り記号が ISA インターチェンジ制御ヘッダーで定義されます。  
  
 インターチェンジの制御および機能グループ ヘッダーとトレーラーはエンベロープ セグメントとして示されます。 BizTalk Server では、トランザクション セットとして受信したインターチェンジを分割、コンテキスト プロパティとしてこれらのエンベロープ セグメントが保存されます。 ルーティングのために役立つ主なエンベロープ プロパティは、個々 のプロパティとして使用できます。 これは、メッセージ自体の一部をエンベロープ データがこの場合は、インターチェンジが保存されるときに発生しません。  
  
 ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信メッセージを生成しますに基づいてヘッダーとトレーラー取引先アグリーメント (パーティが特定されていない場合はグローバル アグリーメント) を作成します。  
  
 ヘッダーおよびトレーラのフィールドと、インターチェンジでこれらを分離するために使用する区切り文字、2 つのパーティ間のアグリーメントで定義します。 アグリーメントに対して定義されている、区切り文字は、インターチェンジ、グループ、またはトランザクション セット ヘッダーやトレーラ フィールドのいずれかの定義では使用されませんする必要があります。 送信側の EDI アセンブラーで処理インターチェンジが失敗する場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]または受信側パーティの逆アセンブラーにします。 インターチェンジ失敗 EDI アセンブラーで、送信バッチの場合、アセンブラーはヘッダー制御 (サービス) スキーマと照らし合わせたエンベロープを検証します。 インターチェンジがバッチでない場合、EDI アセンブラーがシリアル化できますが、受信側アグリーメントで、逆アセンブラーで処理は失敗します。  
  
## <a name="x12-headers-and-trailers"></a>X12 ヘッダーとトレーラー  
 ヘッダーと X12 エンコード メッセージのトレーラーは次のとおりです。  
  
```  
ISA Interchange Control Header  
  GS Functional Group Header  
    ST Transaction Set Header  
    SE Transaction Set Trailer  
  GE Functional Group Trailer  
IEA Interchange Control Trailer  
```  
  
 ISA ヘッダーが IEA トレーラー直後がある場合、インターチェンジが空です。 トランザクション セットが存在する場合、GS ヘッダーおよび GE トレーラー必要があります。それ以外の場合、条件付きです。  
  
 X12 でエンコードされたメッセージの ISA インターチェンジ制御ヘッダー フィールドでは、固定長です。 一部のフィールドには、フィールドの固定長未満の値を入力できます。 これを行う場合、インターチェンジする必要がありますよう含まれます (文字列フィールド) の末尾のスペースまたは先頭に 0 (数値フィールド) の各フィールドが必要な長さ。 送信インターチェンジを作成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は末尾のスペースまたは先頭に 0、適切な長さのインターチェンジ制御ヘッダーを作成することを入力します。 GS グループのヘッダー フィールドと ST トランザクションは、フィールドにはない固定長のヘッダーを設定します。  
  
 X12 でエンコード、機能セキュリティ ヘッダー、機能保証ヘッダー、機能セキュリティ値セグメント、および機能セキュリティ トレーラー セグメントは説明しませんの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI および AS2 します。 これらのセグメントを持つインターチェンジを受信すると、これらが認識されないセグメントであることを示すエラー ログで中断されます。  
  
 ST01 フィールドは、トランザクション セット ID コードです。ST02 フィールドは、トランザクション セット制御番号です。 ST03 フィールドは、スキーマ バージョン識別子です。 SE01 フィールドは、トランザクション セットに含まれるセグメントの数を示しますSE02 フィールドは、(トランザクション セット制御番号)、ST02 フィールドと同じです。 受信メッセージを解析するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]はトランザクション セットのセグメントの数が SE01 フィールドの値に対応していることを確認します。 送信メッセージを生成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をトランザクション セットのセグメントの正しい数が SE01 フィールドを設定します。  
  
 送信 EDI インターチェンジにシリアル化される XML トランザクション セットには、トランザクション セット ヘッダーとトレーラーが必要です。 ただし、EDI アセンブラーは、トランザクション セット ヘッダーまたはトレーラーがなくても、メッセージを処理します。 XML トランザクション セットでは、X12 および EDIFACT スキーマのトランザクション セット ヘッダーおよびトレーラー セグメントはオプションです。 トランザクションにヘッダーまたはトレーラーがない場合、EDISend または AS2EDISend 送信パイプラインの EDI アセンブラーは、トランザクションにトランザクション セット ヘッダー値およびトレーラー値を追加します。 これらの値は、マッピングまたは計算に基づきます。 EDI アセンブラーは、この処理をインターチェンジ XML (保護されたバッチ)、バッチ トランザクション セット XML、およびトランザクション セット XML に対して行います。 詳細については、次を参照してください。 [X12 トランザクション セット ヘッダーおよびトレーラ セグメント](../core/how-the-edi-assembler-works.md#BKMK_X12)または[EDIFACT トランザクション セット ヘッダーおよびトレーラ セグメント](../core/how-the-edi-assembler-works.md#BKMK_EDIFACT)します。  
  
## <a name="edifact-headers-and-trailers"></a>EDIFACT ヘッダーとトレーラー  
 ヘッダーと EDIFACT でエンコードされたメッセージのトレーラーは次のとおりです。  
  
```  
UNA Service String Advice  
UNB Interchange Control Header  
  UNG Functional Group Header  
    UNH Message Header  
    UNT Message Trailer  
  UNE Functional Group Trailer  
UNZ Interchange Control Trailer  
```  
  
 UNA ヘッダーは必要ありません。 UNB ヘッダーが必要です。 UNA ヘッダーが存在する場合は、受信メッセージの処理時に使用する区切り記号が含まれていますそれ以外の場合は、EfactDelimiters パイプライン プロパティに対して定義されている区切り記号が使用されます。  
  
 UNB ヘッダーは UNZ トレーラーですぐに従うと、インターチェンジが空です。 UNG ヘッダーは UNE トレーラーですぐに従うと、グループが空です。 UNG ヘッダーおよび UNE トレーラーの組み合わせは条件付きと、メッセージに存在する必要はありません。  
  
## <a name="see-also"></a>参照  
 [EDI メッセージの構造](../core/edi-message-structure.md)