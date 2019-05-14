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
ms.openlocfilehash: 4c5ee34c80b2bcdc0d0abfe085e174bf5ee6b599
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353277"
---
# <a name="customizing-enumerations-in-the-envelope-schema"></a>エンベロープ スキーマで列挙のカスタマイズ
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービス (エンベロープ) スキーマで ID フィールドの列挙をカスタマイズできます。 これを使用すると、受信または送信を標準以外の値を持つインターチェンジ (セット、X12 で定義されている値の範囲外標準化団体) エンベロープの送信者または受信者 ID フィールドにします。 また、アグリーメント プロパティの定義のヘッダー値のドロップダウン リストで使用できる修飾子を変更することもできます。  
  
> [!IMPORTANT]
>  該当する標準のすべてのトランザクションに変更が適用されるスキーマを変更する場合。 1 つのパーティのエンベロープ スキーマに変更を加えることはできません。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 、、の製品に付属している microsoft.biztalk.edi.baseartifacts.dll の静的サービス スキーマから使用できる値の一覧を取得します。 値の基本セットを拡張するには、サービス スキーマの拡張機能をデプロイする必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] サービス (エンベロープ) スキーマ テンプレートの列挙体を変更するのに使用できるを提供します。 これらのサービス スキーマは、X12_ServiceSchemaExtension.xsd および EDIFACT_ServiceSchemaExtension.xsd が。 各カスタム スキーマは、標準に応じて、次の名前空間のいずれかになります。 この名前空間を変更することはできません。  
  
|Standard|Namespace|  
|--------------|---------------|  
|X12 および HIPAA|`http://schemas.microsoft.com/BizTalk/EDI/X12/2006`|  
|EDIFACT|`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`|  
  
 BizTalk エディタでスキーマに変更を加える[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)](次の手順を参照してください)。 必要な変更を行った後、スキーマを展開する必要があります。  
  
 受信と送信の両方の側でときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンベロープ セグメント (ISA および X12 の場合、または UNB の場合は GS、edifact UNG) を検証しますが、名前空間に基づいたカスタム サービス スキーマの存在をチェックします。 カスタム スキーマが展開されている場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は標準のサービス スキーマでは、そのスキーマをマージし、カスタムと標準の両方の列挙を使用値を指定します。 列挙リストを拡張するスキーマをカスタマイズすることができますが、そこから値を削除することはできません。 カスタム スキーマが展開されていない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]は標準のサービス スキーマを使用します。  
  
 カスタム スキーマを配置した後、[!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)]ユーザー インターフェイスで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールはで、適切なドロップダウン リストを設定するカスタム列挙の値を使用するが、[!INCLUDE[TPM_abbrev](../includes/tpm-abbrev-md.md)]プロパティ ページ。 カスタム スキーマを展開していない場合[!INCLUDE[TPM_abbrev](../includes/tpm-abbrev-md.md)]標準のサービス スキーマの列挙の値が使用されます。 さらに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ランタイムでは、カスタムの列挙は、メッセージの検証に使用します。  
  
 提供される XML ツールを使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を持つインスタンスを検証して、エンベロープ サービス スキーマをカスタマイズした、ドキュメント (トランザクション セット) をさらに、BizTalk プロジェクト内のカスタム サービス スキーマを含める必要がありますスキーマと、必要に応じて、バッチ スキーマ。 これは、エンベロープがない、トランザクション セットのインスタンスを検証する場合は必要はありません。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
##  <a name="BKMK_Env_Can"></a> 変更可能なエンベロープ フィールド  
 次のエンベロープ フィールドのみを変更できます。 拡張機能スキーマには、これらのフィールドのみが含まれます。 追加サービスの拡張機能のスキーマの他のフィールドには、処理に影響はありません。  
  
|Standard|フィールド|  
|--------------|-----------|  
|X12 および HIPAA|[Isa01]: 認証修飾子<br /><br /> [Isa03]: セキュリティ修飾子<br /><br /> [Isa05]: 送信者 ID 修飾子<br /><br /> [Isa07]: 受信者 ID 修飾子<br /><br /> [Gs01]: 機能コード<br /><br /> [Gs07]: 担当機関|  
|EDIFACT|[Unb2.2]: 送信者コードの修飾子<br /><br /> [Unb3.2]: 受信者コードの修飾子|  
  
## <a name="envelope-fields-that-should-not-be-modified"></a>変更しないでくださいエンベロープ フィールド  
 エンベロープの一部のフィールドは、エンジンの動作をドライブします。 その結果、これらのフィールドのいずれかの既存の列挙リストに値を追加する必要がありますできません。 これらのフィールドは次のとおりです。  
  
|Standard|フィールド|  
|--------------|-----------|  
|X12 および HIPAA|[Isa11]: インターチェンジ制御標準識別子<br /><br /> [Isa12]: インターチェンジ制御バージョン番号<br /><br /> [Isa14]: 受信確認要求|  
|EDIFACT|[Unb1.1]: 構文識別子<br /><br /> [Unb1.2]: 構文のバージョン番号<br /><br /> [Unb9]: 受信確認要求|  
  
### <a name="to-customize-an-enumeration-in-the-envelope-schema"></a>エンベロープ スキーマで列挙をカスタマイズするには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、新しいプロジェクトを作成します。  
  
2. X12_ServiceSchemaExtension.xsd スキーマ (X12 または HIPAA の列挙型を変更) するまたは EDIFACT_ServiceSchemaExtension.xsd スキーマを追加[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]を BizTalk プロジェクト、BizTalk エディターで xsd_schema \edi にあります。 スキーマを開きます。  
  
3. 列挙体の値を変更するで列挙を選択します。、**プロパティ**ウィンドウを開く省略記号をクリックして、**列挙エディター**します。 必要に応じて、各行に 1 つの値が存在する値のリストを追加、**値**ウィンドウ。 **[OK]** をクリックします。  
  
   > [!IMPORTANT]
   >  サービス スキーマの名前空間を変更することはできません。 スキーマは、製品にインストールされている元の拡張機能のスキーマと同じ名前空間とルート ノードの名前が必要です。  
  
   > [!NOTE]
   >  スキーマに新しいフィールドを追加する場合は、そのフィールドは無視されます。 示されているフィールドのみ、[エンベロープ フィールドを変更できること](../core/customizing-enumerations-in-the-envelope-schema.md#BKMK_Env_Can)前のセクションを変更することができます。  
  
4. スキーマを保存します。  
  
5. スキーマを右クリックし、をクリックして**デプロイ**します。  
  
   > [!NOTE]
   >  スキーマは、現在の BizTalk グループにデプロイする必要があります。  
  
## <a name="see-also"></a>参照  
 [EDI スキーマの開発](../core/developing-edi-schemas.md)   
 [EDI スキーマの変更](../core/modifying-edi-schemas.md)