---
title: "作成または編集、ホーム組織 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- home organizations, about home organizations
- home organizations, modifying
- creating, home organizations
- modifying, home organizations
- home organizations
- home organizations, creating
ms.assetid: b54afb84-2f16-4516-8701-b03301476362
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bc8a298686772d354c934d76fbcb7dbbb8146f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-or-editing-a-home-organization"></a>作成またはホーム組織を編集します。
ここでは、ホーム組織の作成方法または編集方法について説明します。 ホーム組織の構成では、組織の説明と分類、発信元の否認不可期間の設定、および連絡先情報の提供を行います。  
  
 パートナー構成と異なり、ホーム組織の構成には、署名証明書と暗号化解除証明書は含まれません。 BizTalk グループの署名証明書を構成する、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。 BizTalk ホスト (BizTalkServerApplication および BizTalkIsolatedHost) の暗号化解除証明書は、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで構成します。  
  
 1 つの会社または展開の範囲内に 2 つのホーム組織を作成できます。 このような例として、メッセージの優先処理を作成するインスタンスがあります。この場合、一方の組織に送信されるメッセージは、もう一方の組織に送信されるメッセージよりも優先されます。 複数のホーム組織を作成する場合は、各ホーム組織を一意に識別するために個別の DUNS 番号を指定する必要があります。 DUNS 番号によって RosettaNet 接続が定義されます。  
  
 次の表に、ホーム組織記述における設定をタブごとに整理して示します。ホーム組織の作成方法と編集方法については、表の後の手順を参照してください。  
  
|タブ|設定|使用方法|  
|---------|-------------|-----------|  
|**全般**|**名前**|ホーム組織の名前。<br /><br /> 必須フィールド。<br /><br /> 最大長: 255|  
|**全般**|**[GBI]**|ホーム組織のグローバル ビジネス ID (GBI)。 これは、長さで、9 桁の数字にする必要があり、DUNS 番号に対応する必要があります。<br /><br /> 必須フィールド。|  
|**全般**|**Description**|ホーム組織の識別に役立つ説明。|  
|**全般**|**ホーム組織の分類**|組織の性質。<br /><br /> 指定できます**エンドユーザー**、**政府機関**、 **Financier**、**製造元**、**小売業者**、 **買い物**、 **Freight フォワーダー**、または**Marketplace**です。<br /><br /> アグリーメントの [カスタム プロパティ] タブで HPCC カスタム プロパティを入力すると、メッセージの Service Header に含まれるホーム組織の分類に別の値を入力し、このプロパティをオーバーライドすることができます。 詳細については、次を参照してください。[を作成するか、契約の編集](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)です。|  
|**連絡先のプロパティ**|**連絡先の名前**|ホーム組織での連絡先の名前。<br /><br /> 必須フィールド。|  
|**連絡先のプロパティ**|**[電子メール アドレス]**|ホーム組織での連絡先の電子メール アドレス。<br /><br /> 必須フィールド。|  
|**連絡先のプロパティ**|**電話番号**|ホーム組織での連絡先の電話番号。<br /><br /> 必須フィールド。|  
|**連絡先のプロパティ**|**Fax 番号**|ホーム組織での連絡先の FAX 番号。<br /><br /> 必須フィールド。|  
|**連絡先のプロパティ**|**サプライ チェーン コード**|ホーム組織のサプライ チェーン コード。<br /><br /> 必須フィールド。|  
  
### <a name="to-create-a-home-organization-definition"></a>ホーム組織の定義を作成するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
2.  BTARN 管理コンソールで、[[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]] を展開します。  
  
3.  右クリック**ホーム組織**、 をポイント**新規**、クリックして**ホーム組織**です。  
  
4.  新しいホーム組織のプロパティ ダイアログ ボックスで、**全般**と**連絡先のプロパティ**タブで、設定値を入力します。 これらの設定の詳細については、上の表を参照してください。  
  
5.  **[OK]**をクリックします。  
  
### <a name="to-edit-a-home-organization"></a>ホーム組織を編集するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリック[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**.  
  
2.  BTARN 管理コンソールで、[[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]] を展開します。  
  
3.  をクリックして**ホーム組織**です。  
  
4.  編集、およびをクリックするホーム組織を右クリックして**プロパティ**です。  
  
5.  *\<ホーム組織 >*プロパティ ダイアログ ボックスで、**全般**と**連絡先のプロパティ**タブは必要に応じて設定を変更します。 これらの設定の詳細については、上の表を参照してください。  
  
6.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [構成、証明書、データベース、およびセキュリティを管理します。](manage-configuration-certificates-databases-security.md)   
 [BTARN 構成の管理](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)