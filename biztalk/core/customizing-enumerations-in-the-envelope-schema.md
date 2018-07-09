---
title: エンベロープ スキーマで列挙のカスタマイズ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b053d82-753f-4a05-9922-fa5dbd073ba9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8897130974f0d2248de49d2fd84646bb0cbafd7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991995"
---
# <a name="customizing-enumerations-in-the-envelope-schema"></a>エンベロープ スキーマでの列挙のカスタマイズ
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、サービス (エンベロープ) スキーマで ID フィールドの列挙をカスタマイズできます。 これにより、エンベロープの送信者 ID フィールドまたは受信者 ID フィールドに標準以外の値 (X12 標準の本文に定義された値以外の値セット) を使用しているインターチェンジの送受信を行うことができます。 また、アグリーメント プロパティを定義する際に、ヘッダー値のドロップダウン リストで使用できる修飾子を変更することもできます。  
  
> [!IMPORTANT]
>  スキーマを変更すると、該当する標準のすべてのトランザクションに変更が適用されます。 1 つのパーティのエンベロープ スキーマに変更を加えることはできません。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、製品に付属している Microsoft.BizTalk.Edi.BaseArtifacts.dll の静的サービス スキーマから使用可能な値の一覧を組み込みます。 値の基本セットを拡張するには、サービス スキーマ拡張を開発し、展開する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービス (エンベロープ) スキーマ テンプレートの列挙体を変更するのに使用できるを提供します。 これらのサービス スキーマは、X12_ServiceSchemaExtension.xsd および EDIFACT_ServiceSchemaExtension.xsd が。 各カスタム スキーマには、標準に応じて、次のいずれかの名前空間が存在します。 この名前空間は変更できません。  
  
|Standard|Namespace|  
|--------------|---------------|  
|X12 および HIPAA|`http://schemas.microsoft.com/BizTalk/EDI/X12/2006`|  
|EDIFACT|`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`|  
  
 スキーマの変更は、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の BizTalk エディターで行います (次の手順を参照)。 必要な変更を行った後で、スキーマを展開する必要があります。  
  
 受信側と送信側の両方で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がエンベロープ セグメント (X12 の場合は ISA および GS、EDIFACT の場合は UNB および UNG) を検証するときに、名前空間に基づいたカスタム サービス スキーマが存在するかどうかを確認します。 カスタム スキーマを展開する場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はこのスキーマと標準のサービス スキーマをマージし、指定された場所のカスタムの列挙値と標準の列挙値の両方を使用します。 スキーマをカスタマイズして列挙一覧を拡張できますが、一覧から値を削除することはできません。 カスタム スキーマを展開しない場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は標準のサービス スキーマを使用します。  
  
 カスタム スキーマが展開されると、[!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] 管理コンソールの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のユーザー インターフェイスでは、カスタム列挙の値を使用して、[!INCLUDE[TPM_abbrev](../includes/tpm-abbrev-md.md)] プロパティ ページの適切なドロップダウン リストに値を設定します。 カスタム スキーマを展開していない場合、[!INCLUDE[TPM_abbrev](../includes/tpm-abbrev-md.md)] は標準のサービス スキーマの列挙の値を使用します。 また、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ランタイムは、メッセージの検証にカスタム列挙を使用します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に用意されている XML ツールを使用して、エンベロープを使用するインスタンスを検証し、サービス スキーマをカスタマイズする場合、ドキュメント (トランザクション セット) スキーマや (必要に応じて) バッチ スキーマだけでなく、カスタム サービス スキーマを BizTalk プロジェクトに含める必要があります。 エンベロープを使用しないトランザクション セット インスタンスを検証する場合、これは不要です。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
##  <a name="BKMK_Env_Can"></a> 変更可能なエンベロープ フィールド  
 次のエンベロープ フィールドのみ変更できます。 拡張スキーマには、これらのフィールドのみ含まれています。 サービス拡張スキーマに他のフィールドを追加しても、処理には影響しません。  
  
|Standard|フィールド|  
|--------------|-----------|  
|X12 および HIPAA|[ISA01]: 認証修飾子<br /><br /> [ISA03]: セキュリティ修飾子<br /><br /> [ISA05]: 送信者 ID 修飾子<br /><br /> [ISA07]: 受信者 ID 修飾子<br /><br /> [GS01]: 機能コード<br /><br /> [GS07]: 担当機関|  
|EDIFACT|[UNB2.2]: 送信者コードの修飾子<br /><br /> [UNB3.2]: 受信者コードの修飾子|  
  
## <a name="envelope-fields-that-should-not-be-modified"></a>変更できないエンベロープ フィールド  
 エンベロープの一部のフィールドは、エンジンの動作に影響します。 そのため、このようなフィールドでは、既存の列挙一覧に値を追加しないでください。 このようなフィールドは以下のとおりです。  
  
|Standard|フィールド|  
|--------------|-----------|  
|X12 および HIPAA|[ISA11]: インターチェンジ制御標準識別子<br /><br /> [ISA12]: インターチェンジ制御バージョン番号<br /><br /> [ISA14]: 受信確認要求|  
|EDIFACT|[UNB1.1]: 構文識別子<br /><br /> [UNB1.2]: 構文のバージョン番号<br /><br /> [UNB9]: 受信確認要求|  
  
### <a name="to-customize-an-enumeration-in-the-envelope-schema"></a>エンベロープ スキーマで列挙をカスタマイズするには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で新しいプロジェクトを作成します。  
  
2. BizTalk エディターで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI にある X12_ServiceSchemaExtension.xsd スキーマ (X12 または HIPAA の列挙を変更する場合) または EDIFACT_ServiceSchemaExtension.xsd スキーマを BizTalk プロジェクトに追加します。 スキーマを開きます。  
  
3. 列挙体の値を変更するで列挙を選択します。、**プロパティ**ウィンドウを開く省略記号をクリックして、**列挙エディター**します。 必要に応じて、各行に 1 つの値が存在する値のリストを追加、**値**ウィンドウ。 **[OK]** をクリックします。  
  
   > [!IMPORTANT]
   >  サービス スキーマの名前空間は変更できません。 スキーマは、製品にインストールされている元の拡張スキーマと同じ名前空間とルート ノード名を持つ必要があります。  
  
   > [!NOTE]
   >  新しいフィールドをスキーマに追加しても、そのフィールドは無視されます。 示されているフィールドのみ、[エンベロープ フィールドを変更できること](../core/customizing-enumerations-in-the-envelope-schema.md#BKMK_Env_Can)前のセクションを変更することができます。  
  
4. スキーマを保存します。  
  
5. スキーマを右クリックし、をクリックして**デプロイ**します。  
  
   > [!NOTE]
   >  スキーマは、現在の BizTalk グループに展開する必要があります。  
  
## <a name="see-also"></a>参照  
 [EDI スキーマの開発](../core/developing-edi-schemas.md)   
 [EDI スキーマの変更](../core/modifying-edi-schemas.md)