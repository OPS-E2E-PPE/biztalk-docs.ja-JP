---
title: メッセージのエンコーディング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, encodings
- messages, code samples
- encoding [messages]
- code samples
ms.assetid: 360638c0-4094-428f-a7c7-306a5f95a6bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36063416e1c5d1f30c9cb9c26056299f0b926a50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204794"
---
# <a name="message-encodings"></a>メッセージ エンコーディング
役に立つに HL7 の順序でメッセージのセマンティクスを定義するのに十分ではありません。 メッセージの内容が特定されると、標準は、実際のインターフェイスでは、そのコンテンツを表現する方法を説明するがします。 つまり、ある必要があります指定された「メッセージ エンコード」です。 HL7 バージョン 2 には、メッセージ エンコーディング、カスタム区切り記号ベース エンコーディング、および XML エンコーディングの 2 つの形式がサポートしています。  
  
 HL7 では、元の区切り記号ベースのエンコードをできるだけ多くのメッセージのサイズを減らすために選択されました。 たとえば、区切り文字が位置の固定セット内の各要素を移動する構造体への要素を別々 のデータ構造体を比較する場合の区切り記号ベースの構造体は、はるかに高経済的) メッセージでは、いくつかの要素、および b) が含まれない場合要素では、許可されているすべての領域は入力しません。 区切り記号ベースの構造でのみ、オーバーヘッドは、自身の区切り記号です。  
  
 元の HL7 のエンコードには、各メッセージが MSH セグメント内で宣言する 5 つの区切り記号を定義します。 これは、情報を示します。  
  
-   セグメント  
  
-   フィールド  
  
-   コンポーネント  
  
-   これらのサブコンポーネント  
  
-   繰り返し (フィールド、コンポーネントまたはサブコンポーネント)  
  
 区切り記号は、エンコーディングの基本的な側面にあるために必要がありますを定義することに最初に注意してください。 この結果は、ことはありませんサブ サブの区切り記号です。 ときに、この制限には、新しいデータ型のデザイン時に残念ながら効果があります。  
  
 年 6 月の 2003 では、HL7 は、HL7 バージョン 2、XML エンコードの構文、Release 1 を公開します。 この標準 HL7 バージョン 2.3.1 と 2.4 メッセージの場合の代替のエンコード規則を定義し、後続の HL7 の代替のエンコード規則を決定するためのメカニズムを提供 2.X バージョン。 基本的には、この新しい標準は、Version 2.3.1 と V2.4 抽象メッセージ、セグメント、フィールド、およびデータ型の XML 要素タグを定義し、標準バージョン 2 の後続バージョンで作成された新しい構造体に必要なタグを定義するための規則を作成します。 この標準を定義するプロセスは、バージョン 2.4 および 2.5 での機能強化の系列につながっています。 これには、XML タグの作成の原因で、基になる標準従来からのあいまいさを解決する必要があるためにが発生しました。 ) 適切に定義されたメッセージの構造体のコードを抽象にイベントを発生させる、b) 繰り返し抽象メッセージを含むセグメントのグループが正式に特定され、という名前に関連付けられているメッセージ内のバリエーションを示すために作成された as a result、c)、およびローカル定義済みのデータ型、CM は、特定の種類に置き換えられました。  
  
 たとえば、従来のパイプ区切り形式を使用して、単純な受信確認メッセージは、次のように。  
  
```  
MSH|^~\&|LAB|767543|ADT|767543|199003141304-0500||ACK^^ACK|XX3657|P|2.4  
MSA|AR|ZZ9380  
ERR|PID^1^16^103&Table value not found&HL70357  
```  
  
 これに対し、次は、同じメッセージを XML ドキュメントとして表されます。  
  
```  
<ACK  
xmlns="urn:hl7-org:v2xml"  
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xsi:schemaLocation="urn:hl7-org:v2xml ACK.xsd">  
   <MSH>  
      <MSH.1>|</MSH.1>  
      <MSH.2>^~\&</MSH.2>  
      <MSH.3>  
         <HD.1>LAB</HD.1>  
      </MSH.3>  
      <MSH.4>  
         <HD.1>767543</HD.1>  
      </MSH.4>  
      <MSH.5>  
         <HD.1>ADT</HD.1>  
      </MSH.5>  
      <MSH.6>  
         <HD.1>767543</HD.1>  
      </MSH.6>  
      <MSH.7>  
         <TS.1>199003141304-0500</TS.1>  
      </MSH.7>  
      <MSH.9>  
         <MSG.1>ACK</MSG.1>  
         <MSG.3>ACK</MSG.3>  
      </MSH.9>  
      <MSH.10>XX3657</MSH.10>  
      <MSH.11>  
         <PT.1>P</PT.1>  
      </MSH.11>  
      <MSH.12>  
         <VID.1>2.4</VID.1>  
      </MSH.12>  
   </MSH>  
   <MSA>  
      <MSA.1>AR</MSA.1>  
      <MSA.2>ZZ9380</MSA.2>  
   </MSA>  
   <ERR>  
      <ERR.1>  
         <ELD.1>PID</ELD.1>  
         <ELD.2>1</ELD.2>  
         <ELD.3>16</ELD.3>  
         <ELD.4>  
            <CE.1>103</CE.1>  
            <CE.2>Table value not found</CE.2>  
            <CE.3>HL70357</CE.3>  
         </ELD.4>  
      </ERR.1>  
   </ERR>  
</ACK>  
```  
  
 次の関数の[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) これらの要件をサポートします。  
  
-   パイプ区切りおよび XML エンコーディングのサポート。  
  
-   XML ストレージとパイプの翻訳のサポートには、エンコーディングが区切られます。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)