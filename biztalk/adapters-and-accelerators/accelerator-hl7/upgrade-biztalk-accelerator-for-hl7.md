---
title: BizTalk Accelerator for HL7 にアップグレード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 91b6747f-e560-4cf8-99b5-af0d150599bf
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 245d59e54a39cb77a71fc546920542619a4aeb3f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977643"
---
# <a name="upgrade-biztalk-accelerator-for-hl7"></a>アップグレードの BizTalk Accelerator 用 HL7
概要については、[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]プロセスをアップグレードします。 

<a name="BKMK_BeforeUpgrade"></a>   
## <a name="before-you-upgrade"></a>アップグレードする前に  

- アップグレードを実行しているユーザーは、BizTalk 管理者グループのメンバーである必要があります。  

- アップグレードを実行するときに、SQL Server (MSSQLSERVER) サービスが実行する必要があります。  

- アップグレードするサイレント インストールは実行されません。  

- セットアップ プログラムでは、既存の移行をアップグレードするときに[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]より新しいバージョンに情報を構成します。  

- アップグレードすると、レジストリ キーとデータベースに自動的にバックアップされます。  

- 内のファイル、 *\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for HL7 のフォルダーが更新されます。  

> [!IMPORTANT]
>  アップグレードがアップグレードされたファイル用の新しいフォルダーを作成していないもは既存のフォルダーの名前を変更します。  

<a name="BKMK_UpgradePaths"></a>   
## <a name="supported-upgrade-paths"></a>サポートされるアップグレード パス  
 次の表は、サポートされている一覧[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]バージョンをアップグレードすることができます。 「可」は意味、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]バージョンをアップグレードすることができます。 "No"の意味、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]バージョンをアップグレードすることはできません。 場合、[!INCLUDE[HL7_CurrentVersion_abbrev_md](../../includes/hl7-currentversion-abbrev-md.md)]バージョンが記載されていない、そのバージョンをアップグレードすることはできません。  


|                                                                                              | [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)] | [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)] | BizTalk Server 2013 |
|----------------------------------------------------------------------------------------------|------------------------------------------------------|-------------------------------------------------------|---------------------|
| [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2013 |                         はい                          |                          はい                          |         いいえ          |
| [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2010 |                          いいえ                          |                          はい                          |         はい         |

<a name="BKMK_UpgradeSteps"></a>   
## <a name="upgrade-steps"></a>アップグレード手順  

1. アップグレード、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。   

2. バックアップ、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]データベースと、HL7 メッセージ スキーマ。  

3. すべてのファイルをバックアップ、***\<ドライブ\>*:\Program \microsoft BizTalk Accelerator 用 HL7**を変更したフォルダーです。 たとえば、SDK のファイルをバックアップします。  

4. バージョンに適切な更新プログラムをインストール[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]:  

   -   BTAHL7 2010 からアップグレードする場合は、インストール**HL72010Patch.msp**します。  

   -   BTAHL7 2013 からアップグレードする場合は、インストール**HL72013Patch.msp**します。  


5. [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] のセットアップを実行します。 参照してください[for HL7 の BizTalk アクセラレータのインストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)します。  

6. 新しい BTAHL7V2 デプロイ*x*共通プロジェクト。  

7. その他のすべてのアセンブリを再デプロイします。  

8. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] アセンブリを参照するプロジェクトまたはアセンブリを再構築します。 使用して**BTSTask.exe**で\<*ドライブ*\>: \Program Files\Microsoft BizTalk Server\<バージョン\>、手動でこれらのプロジェクトを再デプロイします。  

9. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] サービスを再開します。  

<a name="BKMK_UpgradeMulti"></a>   
## <a name="upgrading-in-a-multi-server-environment"></a>マルチ サーバー環境でのアップグレード  
 マルチ サーバー[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]環境 アップグレード[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]s、アップグレードしてから、[!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)]すべてのサーバー。 次の順序でサーバーを移行します。  

-   BizTalk グループをホストするサーバー  

-   各処理ノード  

-   BAM ポータル サーバー  

## <a name="see-also"></a>参照  
 [BizTalk Accelerator for HL7 のインストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)