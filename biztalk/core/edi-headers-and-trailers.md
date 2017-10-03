---
title: "EDI ヘッダーとトレーラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cf1dae3-9570-413d-a85d-94dcbb561906
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 655a7261da5dc66687fdf0cd623802854c0fa4ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="edi-headers-and-trailers"></a>EDI ヘッダーとトレーラー
EDI インターチェンジの各部分は、ヘッダーとトレーラーで区切られます。これらのヘッダーとトレーラーは、X12 または EDIFACT 標準に準拠している必要があります。 インターチェンジ制御ヘッダーとトレーラーは 1 回のみ出現します。トランザクション セットとグループがインターチェンジ内でバッチ化される場合は、機能グループおよびトランザクション セットのヘッダーとトレーラーが繰り返されます。 各ヘッダーとトレーラーは、ヘッダーとトレーラーの内容に関する情報を含む一連のデータ要素で構成されます。  
  
 X12 と EDIFACT のヘッダーとトレーラーは似ています。 主な違いは、EDIFACT には UNA サービス文字列通知ヘッダーがあり、このヘッダーで、インターチェンジで使用される区切り記号が定義されることです。 X12 エンコードでは、区切り文字が ISA インターチェンジ制御ヘッダーで定義されます。  
  
 インターチェンジ制御ヘッダーとトレーラー、および機能グループ ヘッダーとトレーラーは、エンベロープ セグメントで表されます。 受信したインターチェンジをトランザクション セットとして分割するときに、BizTalk Server はエンベロープ セグメントをコンテキスト プロパティとして保存します。 ルーティングに役立つ主なエンベロープ プロパティは、個別のプロパティとして使用できます。 これは、インターチェンジを保存するときには行われません。その場合、エンベロープ データはメッセージ自体の一部になります。  
  
 送信メッセージの生成時、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は取引先アグリーメント (パーティが特定されていない場合はグローバル アグリーメント) に基づいてヘッダーとトレーラーを作成します。  
  
 ヘッダー フィールドおよびトレーラー フィールドと、インターチェンジでこれらを分離するために使用する区切り文字は、どちらも 2 つのパーティ間のアグリーメントで定義されます。 区切り文字は、アグリーメント用に定義されているため、インターチェンジ、グループ、またはトランザクション セットのヘッダー フィールドやトレーラー フィールドの定義で使用することはできません。 区切り文字をこれらの定義で使用すると、インターチェンジは、送信側 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の EDI アセンブラーまたは受信側パーティの逆アセンブラーで処理に失敗します。 アセンブラーはヘッダー制御 (サービス) スキーマに対してエンベロープを検証するので、送信バッチの場合、インターチェンジは EDI アセンブラーの処理に失敗します。 バッチ化されていないインターチェンジは、EDI アセンブラーではシリアル化されますが、受信側アグリーメントの逆アセンブラーでは処理に失敗します。  
  
## <a name="x12-headers-and-trailers"></a>X12 ヘッダーとトレーラー  
 X12 エンコード メッセージのヘッダーとトレーラーは次のとおりです。  
  
```  
ISA Interchange Control Header  
  GS Functional Group Header  
    ST Transaction Set Header  
    SE Transaction Set Trailer  
  GE Functional Group Trailer  
IEA Interchange Control Trailer  
```  
  
 ISA ヘッダーの直後に IEA トレーラーがある場合が、インターチェンジが空です。 トランザクション セットが存在する場合、GS ヘッダーおよび GE トレーラーが存在する必要があります。それ以外の場合、GS ヘッダーおよび GE トレーラーは条件付きです。  
  
 X12 エンコード メッセージの ISA インターチェンジ制御ヘッダーは固定長です。 一部のフィールドでは、フィールドの固定長未満の値を入力できます。 その場合、各フィールドが必要な長さになるように、インターチェンジには末尾のスペース (文字列フィールドの場合) または先頭の 0 (数値フィールドの場合) を含める必要があります。 送信インターチェンジの作成時に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、適切な長さのインターチェンジ制御ヘッダーを作成するために、末尾のスペースまたは先頭の 0 を入力します。 GS グループのヘッダー フィールドと ST トランザクション セットのヘッダー フィールドは固定長ではありません。  
  
 X12 エンコードでは、機能セキュリティ ヘッダー、機能保証ヘッダー、機能セキュリティ値セグメント、および機能セキュリティ トレーラー セグメントは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI および AS2 の対象外です。 このようなセグメントを含むインターチェンジを受信した場合、これらが認識不可能なセグメントであることを示すエラー ログが生成され、インターチェンジが中断されます。  
  
 ST01 フィールドはトランザクション セット ID コードであり、ST02 フィールドはトランザクション セット制御番号です。 ST03 フィールドはスキーマ バージョン識別子です。 SE01 フィールドはトランザクション セットに含まれるセグメント数を示しており、SE02 フィールドは ST02 フィールド (トランザクション セット制御番号) と同じです。 受信メッセージを解析するときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、トランザクション セットのセグメント数が SE01 フィールドの値に対応していることを確認します。 送信メッセージを生成するときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、SE01 フィールドをトランザクション セットの正しいセグメント数に設定します。  
  
 送信 EDI インターチェンジにシリアル化される XML トランザクション セットには、トランザクション セット ヘッダーとトレーラーが必要です。 ただし、EDI アセンブラーは、トランザクション セット ヘッダーまたはトレーラーがなくても、メッセージを処理します。 XML トランザクション セットでは、X12 および EDIFACT スキーマのトランザクション セット ヘッダーおよびトレーラー セグメントはオプションです。 トランザクションにヘッダーまたはトレーラーがない場合、EDISend または AS2EDISend 送信パイプラインの EDI アセンブラーは、トランザクションにトランザクション セット ヘッダー値およびトレーラー値を追加します。 これらの値は、マッピングまたは計算に基づきます。 EDI アセンブラーは、この処理をインターチェンジ XML (保護されたバッチ)、バッチ トランザクション セット XML、およびトランザクション セット XML に対して行います。 詳細については、次を参照してください。 [X12 トランザクション セット ヘッダーおよびトレーラ セグメント](../core/how-the-edi-assembler-works.md#BKMK_X12)または[EDIFACT トランザクション セット ヘッダーおよびトレーラ セグメント](../core/how-the-edi-assembler-works.md#BKMK_EDIFACT)です。  
  
## <a name="edifact-headers-and-trailers"></a>EDIFACT ヘッダーとトレーラー  
 EDIFACT エンコード メッセージのヘッダーとトレーラーは次のとおりです。  
  
```  
UNA Service String Advice  
UNB Interchange Control Header  
  UNG Functional Group Header  
    UNH Message Header  
    UNT Message Trailer  
  UNE Functional Group Trailer  
UNZ Interchange Control Trailer  
```  
  
 UNA ヘッダーは必要ありません。 UNB ヘッダーは必須です。 UNA ヘッダーが存在する場合は、受信メッセージを処理するときに使用する区切り記号がこのヘッダーに含まれます。それ以外の場合は、EfactDelimiters パイプライン プロパティに定義された区切り文字が使用されます。  
  
 UNB ヘッダーの直後に UNZ トレーラーがある場合は、インターチェンジが空です。 UNG ヘッダーの直後に UNE トレーラーがある場合は、グループが空です。 UNG ヘッダーと UNE トレーラーの組み合わせは条件付きのため、メッセージに存在していなくてもかまいません。  
  
## <a name="see-also"></a>参照  
 [EDI メッセージの構造](../core/edi-message-structure.md)