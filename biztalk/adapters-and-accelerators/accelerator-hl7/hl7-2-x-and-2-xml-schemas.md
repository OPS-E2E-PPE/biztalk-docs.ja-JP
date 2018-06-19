---
title: HL7 2.X および 2. XML のスキーマ |Microsoft ドキュメント
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
ms.openlocfilehash: 5a02c8451dc0dc07b81a824f692203809d52b588
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961904"
---
# <a name="hl7-2x-and-2xml-schemas"></a>HL7 2.X および 2. XML スキーマ
HL7 組織は 2 つのスキーマのセットを公開: HL7 HL7 エンコード メッセージの場合に使用する 2.X スキーマと HL7 2. XML スキーマ、XML でエンコードされたメッセージに使用します。  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] HL7 によるネイティブ 2.X スキーマです。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セットアップに 2.X スキーマ ファイルを読み込み、HL7 \<*ドライブ*\>: \program files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>HL7\Templates\ のアクセラレータSchemas\2.X です。 その結果、HL7 2.X スキーマは、HL7 スキーマの選択で使用できます。 HL7 スキーマの選択で実行する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
 HL7 2. の XML スキーマでは、BTAHL7 の動作は、BTAHL7 セットアップ プログラムは、BTAHL7 プログラム ファイルが、HL7 2. XML スキーマを読み込みませんしようとしている BTAHL7 で動作するためには、HL7 2. XML スキーマの一部を変更します。 HL7 スキーマの選択で使用できるように、必要な変更は、HL7 組織の Web サイトから 2. XML スキーマをダウンロードしてから実行、 **Update2XMLSchema**ツール (詳細については、次を参照してください[。Update2XMLSchema ツール](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md))。 ツールを使用するために必要な HL7 2. XML スキーマは変更は[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]でそれらを配置および\<*ドライブ*\>: \program files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<バージョン\>HL7\Templates\Schemas のアクセラレータです。  
  
 それぞれのスキーマのセットには、一連バージョンにはが含まれています。 HL7 2.X ライブ スキーマ バージョンが 2.5 を通じて 2.1 を含める (詳細については、次を参照してください。 [HL7 バージョン](../../adapters-and-accelerators/accelerator-hl7/hl7-versions.md))。 HL72 です。XML スキーマのバージョンには、2.3.1、2.4、2.5 などがあります。 HL7 2.X スキーマ バージョンでは、旧バージョンと対応します。 旧バージョンとのない HL7 2. XML スキーマのバージョンが準拠していません。  
  
> [!NOTE]
>  2. XML のバージョン 2.4 は旧バージョンとでがないため 2.XML の 2.3.1 に準拠して、エラーが発生する 2.4 2. XML スキーマのバージョンを展開し、2.3.1 に準拠したメッセージのインスタンスを送信した場合のバージョン。 これを修正する必要があります 2.3.1 に対処する別のターゲット名前空間を作成するメッセージ。  
  
 マルチパート HL7 を作成するときに 2.X メッセージ、特定のスキーマ、ボディ部の型を設定する必要があります。 それ以外の場合は、シリアライザーは、メッセージが拒否されます。  
  
 次の表では、BTAHL7 が動作するスキーマの 2 つの基本型について説明します。  
  
|Schema Type|Description|  
|-----------------|-----------------|  
|HL7FF – ER7 エンコード (2.X) スキーマ|BTAHL7 提供 HL7 HL7 Access データベースから派生した 2.X スキーマを含みます。<br /><br /> -特定のバージョン、メッセージの種類、またはイベントに基づいてすべてのスキーマのセット<br />セグメント、データ型、表、ヘッダー、および受信確認 (Ack) の一般的なスキーマ<br /><br /> BTAHL7 では、次のスキーマ テンプレートがサポートされています。<br /><br /> -バージョン 2.1 以降<br />-V2.2<br />-V2.3<br />-V2.3.1<br />-V2.4<br />-V2.5<br /><br /> BTAHL7 セットアップには、V2 がインストールされます。内のスキーマ x \<*ドライブ*\>\Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7\Templates\Schemas です。|  
|HL7XML – 2. XML エンコーディング|BTAHL7 では、次のスキーマがサポートされています。<br /><br /> -V2.3.1<br />-V2.4<br />-V2.5<br /><br /> BTAHL7 セットアップでは、2. XML スキーマはインストールされません。 インストールし、BizTalk エディターでの作業に合わせて変更して、次を参照してください。 [Update2XMLSchema ツール](../../adapters-and-accelerators/accelerator-hl7/update2xmlschema-tool.md)です。|  
  
## <a name="common-schemas"></a>一般的なスキーマ  
 BTAHL7 では、メッセージの種類に固有 HL7 スキーマを使用して、作成してそのメッセージ型のインスタンスの本文を検証します。 また、特定のスキーマに加え、一般的なスキーマを使用します。 BTAHL7 では、一般的な HL7 スキーマを使用して、HL7 メッセージ ヘッダーと受信確認を検証します。 これらのファイルは、受信確認のヘッダーおよび ACK_24_GLO_DEF について MSH_25_GLO_DEF.xsd はします。  
  
 BTAHL7 では、一般的なスキーマを使用してデータ型、セグメント、およびテーブルの値を検証することもできます。 これらのスキーマは、HL7 標準の各バージョンに固有です。 たとえば、バージョン 2.2 メッセージ用の共通スキーマは、datatype_22.xsd、segments_22.xsd、tablevalues_22.xsd です。 BTAHL7 では、これらのスキーマを使用して、データ型、セグメント、およびバージョン 2.2 のすべてのメッセージのテーブルの値を検証します。  
  
## <a name="see-also"></a>参照  
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [BTAHL72X フラット ファイル処理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)   
 [BTAHL72XML 処理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)   
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [HL7 2. XML スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)