---
title: "BizTalk Accelerator 用 HL7 にアップグレード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 91b6747f-e560-4cf8-99b5-af0d150599bf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23b835317d46dfeded65de310f8a813d4ac86749
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="upgrade-biztalk-accelerator-for-hl7"></a>アップグレードの BizTalk Accelerator 用 HL7
概要については、[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]プロセスをアップグレードします。 
  
<a name="BKMK_BeforeUpgrade"></a>   
## <a name="before-you-upgrade"></a>アップグレードする前に  
  
-   アップグレードを実行しているユーザーは、BizTalk 管理者グループのメンバーにする必要があります。  
  
-   アップグレードを実行するときに、SQL Server (MSSQLSERVER) サービスを実行する必要があります。  
  
-   サイレント インストールのアップグレードは実行されません。  
  
-   セットアップ プログラムでは、既存の移行アップグレードすると、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]構成については、新しいバージョンにします。  
  
-   アップグレードすると、レジストリ キーとデータベースに自動的にバックアップされます。  
  
-   内のファイル、 *\<ドライブ >*: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7 フォルダーが更新されます。  
  
> [!IMPORTANT]
>  アップグレードがアップグレードされたファイル用の新しいフォルダーを作成できません。 また、既存のフォルダーの名前は変更。  
  
<a name="BKMK_UpgradePaths"></a>   
## <a name="supported-upgrade-paths"></a>サポートされるアップグレード パス  
 次の表に、サポートされている一覧[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バージョンをアップグレードすることができます。 "Yes"手段、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]バージョンをアップグレードすることができます。 "No"の意味、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]バージョンをアップグレードすることはできません。 場合、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]バージョンが記載されていない、そのバージョンをアップグレードすることはできません。  

||[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]|BizTalk Server 2013|
|---|---|---|---|  
|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2013|はい|可|不可|  
|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2010|不可|はい|はい|  

<a name="BKMK_UpgradeSteps"></a>   
## <a name="upgrade-steps"></a>アップグレード手順  
  
1.  アップグレード、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。   
  
2.  バックアップを[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]データベースと、HL7 メッセージ スキーマ。  
  
3.  下位にあるファイルをバックアップ、  ***\<ドライブ >*: \Program Files\Microsoft BizTalk Accelerator 用 HL7**を変更しているフォルダーです。 たとえば、SDK 内のファイルをバックアップします。  
  
4.  バージョンに適切な更新プログラムをインストール[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]:  
  
    -   BTAHL7 2010 からアップグレードする場合は、インストール**HL72010Patch.msp**です。  
  
    -   BTAHL7 2013 からアップグレードする場合は、インストール**HL72013Patch.msp**です。  
    
  
5.  [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] のセットアップを実行します。 参照してください[用 HL7 BizTalk アクセラレータをインストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)です。  
  
6.  新しい BTAHL7V2 展開*x*共通プロジェクト。  
  
7.  その他のすべてのアセンブリを再展開します。  
  
8.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] アセンブリを参照するプロジェクトまたはアセンブリを再構築します。 使用して**BTSTask.exe**で\<*ドライブ*>: \Program Files\Microsoft BizTalk Server\<バージョン > を手動でこれらのプロジェクトを再展開します。  
  
9. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] サービスを再開します。  
  
<a name="BKMK_UpgradeMulti"></a>   
## <a name="upgrading-in-a-multi-server-environment"></a>マルチ サーバー環境でのアップグレード  
 マルチ サーバー[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]環境、アップグレード[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]秒、およびアップグレードしてから、[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]すべてのサーバーでします。 次の順序でサーバーを移行します。  
  
-   BizTalk グループをホストするサーバー  
  
-   各処理ノード  
  
-   BAM ポータル サーバー  
  
## <a name="see-also"></a>参照  
 [HL7 の BizTalk アクセラレータをインストールします。](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)