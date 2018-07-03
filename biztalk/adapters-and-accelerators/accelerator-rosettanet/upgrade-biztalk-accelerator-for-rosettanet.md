---
title: BizTalk Server では、RosettaNet アクセラレータ (BTARN) のアップグレード |Microsoft Docs"
description: BTARN を BizTalk Server では、現在のバージョンに更新するアップグレードの手順に従います
author: MandiOhlinger
manager: anneta
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ''
ms.author: mandia
ms.openlocfilehash: 80e813ced767cdd56910027b655060e1db9f91fe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011310"
---
# <a name="upgrade-the-rosettanet-accelerator"></a>RosettaNet アクセラレータをアップグレードします。

## <a name="upgrade-overview"></a>アップグレードの概要
BizTalk Accelerator for RosettaNet (BTARN) のインストールの以前のバージョンは、現在のバージョンにアップグレードできます。 アップグレード プロセスには、BizTalk Server をアップグレードして、BTARN のアップグレードが含まれます。  
  
 BTARN の以前のバージョンからアップグレードすることができます、BTARN のインストール プログラムを実行しています。 セットアップでは、BTRAN の構成情報を現在のバージョンに移行します。  
  
 BTARN マルチ サーバー環境では、してから BTARN には、すべての BizTalk Server をアップグレードする必要があります。 次の順序でサーバーを移行します。  
  
- BizTalk グループをホストするサーバー  
  
- 各処理ノード  
  
- BAM ポータル サーバー  
  
  BTARN では、アップグレード プロセスで、次のことを確認します。  
  
- SQL Server (MSSQLSERVER) サービスが実行中であることを確認します。  
  
- サイレント インストールは実行しないでください。  
  
## <a name="upgrade-steps"></a>アップグレード手順  
  
1.  BizTalk Server をアップグレードします。 参照してください[BizTalk Server 新機能については、インストール、構成、およびアップグレード](../../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)します。
  
2.  BTARN データベースとメッセージ スキーマを BTARN をバックアップします。  
  
    > [!NOTE]
    >  安全上の理由から BTARN データベースをバックアップする必要があります。 インストール プログラムは、BTRAN データベースを新しいバージョンに移行します。  
  
3.  すべてのファイルをバックアップ、 *< ドライブ\>*: \Program Files\\Microsoft BizTalk Accelerator の RosettaNet フォルダーに対して行ったが、変更、ファイルなど、sdk。  
  
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
  
    -   [Microsoft.solutions.btarn.schemas.rnpips]  
  
6.  BTARN のインストールを実行します。 参照してください[インストール RosettaNet アクセラレータの構成と](install-configure-biztalk-accelerator-for-rosettanet.md)します。
  
7.  使用**BTSTask.exe** (\Program Files\Microsoft BizTalk Server) を次の順序で BTARN アセンブリを手動で再デプロイします。  
  
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
  
    -   [Microsoft.solutions.btarn.schemas.rnpips]  
  
    > [!NOTE]
    >  詳細については**BTSTask.exe**、BizTalk Server ヘルプの「BTSTask コマンドライン リファレンス」を参照してください。  
  
8.  該当するプロジェクトまたは 1 つまたは複数の [BTARN アセンブリへの参照を持つアセンブリを再構築します。 使用**BTSTask.exe**を手動でこれらのプロジェクトを再デプロイします。  
  
9. 次のコンポーネントについて、IIS の仮想フォルダーを ASP.NET 2.0 から ASP.NET 4.0 にアップグレードします。  
  
    -   BTARNApp  
  
    -   BTARNHttpReceive  
  
10. コンピューターを再起動してすべての変更を適用します。  
  
