---
title: "BizTalk Server では、RosettaNet Accelerator (BTARN) のアップグレード |Microsoft ドキュメント\""
description: "BTARN を BizTalk Server の現在のバージョンに更新するアップグレードの手順に従います"
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 
ms.author: mandia
ms.openlocfilehash: 16e6083f3e5fb1778d77536cd602ee2208c0005f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="upgrade-the-rosettanet-accelerator"></a>RosettaNet accelerator をアップグレードします。

## <a name="upgrade-overview"></a>アップグレードの概要
BizTalk Accelerator for RosettaNet (BTARN) のインストールの以前のバージョンは、現在のバージョンにアップグレードできます。 アップグレード プロセスには、BizTalk Server をアップグレードして、BTARN のアップグレードが含まれます。  
  
 BTARN の以前のバージョンからアップグレードすることができます、BTARN のインストール プログラムを実行します。 セットアップでは、BTRAN の構成情報を現在のバージョンに移行します。  
  
 マルチ サーバー BTARN 環境では、最初に、し、BTARN には、すべての BizTalk Server をアップグレードしてください。 次の順序でサーバーを移行します。  
  
-   BizTalk グループをホストするサーバー  
  
-   各処理ノード  
  
-   BAM ポータル サーバー  
  
 BTARN でアップグレード プロセスは、次を行うことを確認してください。  
  
-   SQL Server (MSSQLSERVER) サービスが実行中であることを確認します。  
  
-   サイレント インストールは実行しないでください。  
  
## <a name="upgrade-steps"></a>アップグレード手順  
  
1.  BizTalk Server をアップグレードします。 参照してください[BizTalk Server 新機能、インストール、構成、およびアップグレード](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)です。
  
2.  BTARN データベースおよび BTARN のメッセージ スキーマをバックアップします。  
  
    > [!NOTE]
    >  安全上の理由から BTARN データベースをバックアップする必要があります。 インストール プログラムは、BTRAN データベースを新しいバージョンに移行します。  
  
3.  下位にあるファイルをバックアップ、 *< ドライブ\>*: \Program Files\\Microsoft BizTalk Accelerator RosettaNet フォルダーに対して行った変更が、たとえば、ファイル、SDK に含まれています。  
  
4.  以前のバージョンの BTRAN アセンブリを参照している場合は、該当するプロジェクトまたはアセンブリの展開を解除します。  
  
5.  Visual Studio で、次の順序で、すべての BTARN アセンブリを手動で解除します。  
  
    -   Microsoft.Solutions.BTARN.CommonTypes  
  
    -   Microsoft.Solutions.BTARN.GlobalSchemas  
  
    -   Microsoft.Solutions.BTARN.PipelineReceive  
  
    -   Microsoft.Solutions.BTARN.PipelineSend  
  
    -   Microsoft.Solutions.BTARN.PrivateInitiator  
  
    -   Microsoft.Solutions.BTARN.PrivateResponder  
  
    -   Microsoft.Solutions.BTARN.PublicInitiator  
  
    -   Microsoft.Solutions.BTARN.PublicResponder  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNIFv11  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNIFv20  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNPIPs  
  
6.  BTARN のインストールを実行します。 参照してください[インストール RosettaNet accelerator を構成および](install-configure-biztalk-accelerator-for-rosettanet.md)です。
  
7.  使用して**BTSTask.exe** (\Program Files\Microsoft BizTalk Server) を次の順序で BTARN アセンブリを手動で再展開します。  
  
    -   Microsoft.Solutions.BTARN.CommonTypes  
  
    -   Microsoft.Solutions.BTARN.GlobalSchemas  
  
    -   Microsoft.Solutions.BTARN.PipelineReceive  
  
    -   Microsoft.Solutions.BTARN.PipelineSend  
  
    -   Microsoft.Solutions.BTARN.PrivateInitiator  
  
    -   Microsoft.Solutions.BTARN.PrivateResponder  
  
    -   Microsoft.Solutions.BTARN.PublicInitiator  
  
    -   Microsoft.Solutions.BTARN.PublicResponder  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNIFv11  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNIFv20  
  
    -   Microsoft.Solutions.BTARN.Schemas.RNPIPs  
  
    > [!NOTE]
    >  詳細については**BTSTask.exe**、BizTalk Server ヘルプの「BTSTask コマンドライン リファレンス」を参照してください。  
  
8.  該当するプロジェクトまたはを 1 つまたは複数の [BTARN アセンブリへの参照を持つアセンブリを再構築します。 使用して**BTSTask.exe**をこれらのプロジェクトを手動で再展開します。  
  
9. 次のコンポーネントについて、IIS の仮想フォルダーを ASP.NET 2.0 から ASP.NET 4.0 にアップグレードします。  
  
    -   BTARNApp  
  
    -   BTARNHttpReceive  
  
10. コンピューターを再起動してすべての変更を適用します。  
  
