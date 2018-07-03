---
title: メッセージのエンコーディング |Microsoft Docs
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
ms.openlocfilehash: 013df4d29604e6dd7ce6d2e486612be303cc5898
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007091"
---
# <a name="message-encodings"></a>メッセージ エンコーディング
HL7 を使用するためにメッセージのセマンティクスを定義するのに十分ではありません。 メッセージの内容を確認すると、実際のインターフェイスでは、そのコンテンツを表す方法を説明する、標準を持ちます。 つまり、必要がある、指定した「メッセージをエンコードする」。 HL7 バージョン 2 では、2 つの形式のメッセージのエンコードと、カスタムの区切り記号ベースのエンコード、XML エンコーディングをサポートします。  
  
 HL7 元区切り記号ベースのエンコード可能な限りメッセージのサイズを小さくことにしました。 たとえばを区切り記号は位置の固定セット内の各要素を移動する構造体への要素を区切るデータ構造体を比較すると、区切り記号ベースの構造体より経済的) メッセージでは、いくつかの要素と b) 一部が含まれない場合要素は、許可されているすべての領域には入力しません。 構造体の区切り記号ベースの唯一のオーバーヘッドは、自身の区切り記号です。  
  
 元の HL7 のエンコードには、各メッセージは MSH セグメント内で宣言する 5 つの区切り記号を定義します。 これらを指定します。  
  
- セグメント  
  
- フィールド  
  
- Components  
  
- サブコンポーネント  
  
- (フィールド、コンポーネントまたはサブコンポーネント) の繰り返し  
  
  区切り記号、エンコーディングの基本的な側面はする必要がありますを定義することに最初に注意してください。 この結果は、あることにないサブ サブの区切り記号です。 この制限には、新しいデータ型のデザイン時に残念な効果があります。  
  
  2003 年 6 月、HL7 は HL7 バージョン 2、XML エンコードの構文、リリース 1 を公開します。 この標準が HL7 バージョン 2.3.1 および 2.4 メッセージの場合、代替のエンコーディング規則を定義し、後続の HL7 の代替のエンコーディング規則を決定するためのメカニズムを提供します 2.X バージョン。 基本的には、この新しい標準は、Version 2.3.1 および V2.4 抽象メッセージ、セグメント、フィールド、およびデータ型の XML 要素タグを定義し、標準バージョン 2 の今後のバージョンの作成、新しい構造に必要なタグを定義するための規則を作成します。 この標準を定義するプロセスは、一連のバージョン 2.4、2.5 での機能強化につながっています。 XML タグの作成により、基になる標準の長期あいまいさに対処する必要があるのため、これが発生しました。 B) 抽象メッセージ セグメントのグループが正式に特定され、という名前の繰り返しのトリガー イベントに関連付けられている抽象メッセージ内のバリエーションを示すコードの構造) 適切に定義されたメッセージが作成されたその、c)、およびローカル定義済みのデータ型、CM は、特定の種類に置き換えられました。  
  
  たとえば、従来のパイプ区切り形式を使用して単純な受信確認メッセージは、次のように。  
  
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
  
 Microsoft BizTalk Accelerator for HL7 の次の関数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) これらの要件をサポートします。  
  
-   パイプ区切り、および XML エンコーディングをサポートします。  
  
-   XML とパイプ間の変換のサポートには、エンコーディングが区切られます。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)