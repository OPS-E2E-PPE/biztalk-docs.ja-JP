---
title: HL7 2.X と 2.xml のスキーマ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, schema types
- HL7-encoded messages
- 2.X schemas
- schemas, HL7 organization
- BTAHL7, HL7 schemas
- HL7, 2.XML schemas
- Update2XMLSchema tool
- schemas, common schemas
- 2.X schemas, about 2.X schemas
- 2.X schemas, compatibility
- 2.XML schemas, compatibility
- messages, HL7-encoded messages
- HL7 Schema Selector
- schemas, 2.XML schemas
- 2.XML schemas
- 2.XML schemas, about 2.XML schemas
- HL7, 2.X schemas
- schemas, compatibility
- common schemas
- schemas, 2.X schemas
ms.assetid: 02532d72-1948-48d8-a8ef-6b5a814eb573
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69dc39b3f61dbb564fc3ef128405b8721633dd2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994187"
---
# <a name="hl7-2x-and-2xml-schemas"></a>HL7 2.X と 2.xml のスキーマ
HL7 組織は、スキーマの 2 つのセットを公開: HL7 2.X スキーマ、HL7 エンコードされたメッセージで使用および HL7 2. XML スキーマ、XML でエンコードされたメッセージに使用します。  

 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]はネイティブに、HL7 動作 2.X スキーマ。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] セットアップに読み込み、HL7 2.X スキーマ ファイル\<*ドライブ*\>: \program files\\Microsoft BizTalk\<バージョン\>HL7\Templates\Schemas\2.X のアクセラレータです。 その結果、HL7 2.X スキーマは HL7 スキーマの選択で使用できます。 Microsoft では、HL7 スキーマの選択を実行する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。  

 HL7 2. XML スキーマでは、BTAHL7 の動作が、BTAHL7 セットアップ プログラムは、BTAHL7 プログラム ファイルが、HL7 2. XML スキーマを 、BTAHL7 で使用するには HL7 2. XML スキーマの一部を変更する必要があります。 HL7 スキーマの選択で利用できるようにし、必要な変更をの HL7 組織の Web サイトから 2. XML スキーマをダウンロードし、実行、 **Update2XMLSchema**ツール (詳細については、次を参照してください[。Update2XMLSchema ツール](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md))。 使用するために、ツールの HL7 2. XML スキーマを変更する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、それらを配置および\<*ドライブ*\>: \program files\\Microsoft BizTalk \<のバージョン\>HL7\Templates\Schemas のアクセラレータです。  

 それぞれのスキーマのセットには、一連バージョンにはが含まれています。 HL7 2.X スキーマのライブ バージョンが 2.5 を通じて 2.1 が含まれます (詳細については、次を参照してください。 [HL7 バージョン](../../adapters-and-accelerators/accelerator-hl7/hl7-versions.md))。 HL72 します。XML スキーマのバージョンには、2.3.1、2.4、2.5 が含まれます。 HL7 2.X スキーマのバージョンは旧バージョンと対応します。 HL7 2. XML スキーマのバージョンが旧バージョンと対応します。  

> [!NOTE]
>  2. XML のバージョン 2.4 は旧バージョンとではありませんので 2.XML の 2.3.1 に準拠している、エラーが発生する 2. XML スキーマのバージョン 2.4 を展開し、2.3.1 に準拠したメッセージのインスタンスを送信した場合のバージョン。 2.3.1 を処理する別のターゲット名前空間を作成する必要がありますこれを修正するメッセージ。  

 作成するときに、マルチパート HL7 2.X メッセージ、特定のスキーマにボディ部の型を設定する必要があります。 それ以外の場合は、シリアライザーは、メッセージが拒否されます。  

 次の表では、2 つの基本的な種類のスキーマが BTAHL7 の機能について説明します。  


|            Schema Type            |                                                                                                                                                                                                                                                                                                   説明                                                                                                                                                                                                                                                                                                    |
|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| HL7FF – ER7 (2.X) スキーマをエンコードします。 | BTAHL7 では、HL7 2.X スキーマの HL7 Access データベースから派生したなど。<br /><br /> -特定のバージョン、メッセージの種類またはイベントに基づいてすべてのスキーマのセット<br />-一般的なスキーマのセグメント、データ型、テーブル、ヘッダー、および受信確認 (Ack)<br /><br /> BTAHL7 では、次のスキーマ テンプレートがサポートされています。<br /><br /> -V2.1<br />-V2.2<br />-V2.3<br />-V2.3.1<br />-V2.4<br />-V2.5<br /><br /> BTAHL7 セットアップでは、V2 をインストールします。内のスキーマ x \<*ドライブ*\>\Program Files\\Microsoft BizTalk Accelerator for HL7\Templates\Schemas します。 |
|      HL7XML – 2. XML エンコーディング      |                                                                                                                                            BTAHL7 では、次のスキーマがサポートされています。<br /><br /> -V2.3.1<br />-V2.4<br />-V2.5<br /><br /> BTAHL7 では、2.xml スキーマがインストールされません。 インストールし、BizTalk エディターを操作するように変更して、次を参照してください。 [Update2XMLSchema ツール](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md)します。                                                                                                                                            |

## <a name="common-schemas"></a>一般的なスキーマ  
 BTAHL7 では、作成し、そのメッセージ型のインスタンスの本文を検証するメッセージの種類に固有の HL7 スキーマを使用します。 また、特定のスキーマに加え、一般的なスキーマを使用します。 BTAHL7 では、一般的な HL7 スキーマを使用して、HL7 メッセージのヘッダーと受信確認を検証します。 これらのファイルは、受信確認のヘッダーと ACK_24_GLO_DEF MSH_25_GLO_DEF.xsd は。  

 BTAHL7 では、一般的なスキーマを使用してデータ型、セグメント、およびテーブルの値を検証することもできます。 これらのスキーマは、HL7 標準の各バージョンに固有です。 たとえば、バージョン 2.2 メッセージ用の一般的なスキーマは、datatype_22.xsd、segments_22.xsd、tablevalues_22.xsd です。 BTAHL7 では、これらのスキーマを使用して、データ型、セグメント、およびバージョン 2.2 のすべてのメッセージのテーブルの値を検証します。  

## <a name="see-also"></a>参照  
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [BTAHL72X フラット ファイル処理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)   
 [BTAHL72XML 処理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)   
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [HL7 2. XML スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)