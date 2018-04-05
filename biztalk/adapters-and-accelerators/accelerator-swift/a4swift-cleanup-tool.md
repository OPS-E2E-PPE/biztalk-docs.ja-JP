---
title: A4SWIFT クリーンアップ ツール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- A4SWIFT Cleanup tool
ms.assetid: e694f824-6097-4d60-bc7b-b4f1a40acea0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b2d0e251bf5e8a4169ff0d86cc6635944ca12e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="a4swift-cleanup-tool"></a>A4SWIFT クリーンアップ ツール
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]クリーンアップ ツールを持つサーバーを準備することができます、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]の新規インストール用にインストールされている[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]です。 ツールは、契約、部門、およびビジネス ルール エンジン (BRE) ポリシーなど、A4SWIFT の成果物を削除し、アセンブリの展開を解除します。 ツールを実行して、A4SWIFT の多くのアイテムを手動で削除されないようにすることができます、展開解除が参照されるアセンブリを他のアセンブリからの問題が解決します。  
  
 クリーンアップ ツールを実行するときに、成果物を削除した後、コンピューター (既定)、またはアンインストール A4SWIFT にインストールされている A4SWIFT のままの選択肢がありません。 A4SWIFT をアンインストールする前に、ツールを実行する必要があります。  
  
> [!CAUTION]
>  運用環境では、A4SWIFT クリーンアップ ツールを使わないでください。 このツールはマルチ サーバー展開ではなく、単一サーバーの開発環境で使用するものです。  
  
> [!NOTE]
>  既定では、クリーンアップ ツール機能しません、他の言語が英語以外の。 クリーンアップ ツールは、ローカライズされたコンピューターで動作するように環境を変更することができます、ただし、します。 FormPublish ツールを実行して、t パラメーターとテンプレート ドキュメント ライブラリのローカライズされた文字列と**t:VorLagen**ドイツ語の環境でします。 クリーンアップ ツールは、ローカライズされた環境で実行できます。  
  
 次では true、クリーンアップ ツールを実行します。  
  
-   メンバーである必要がある必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]ツールを実行するサーバーにインストールする必要があります。  
  
-   MrsrConfiguration.dll、Shared.dll、および RuleEngineExtension.dll はツールを実行するサーバーに配置する必要があります。  
  
## <a name="what-the-cleanup-tool-does"></a>クリーンアップ ツールの実行内容  
 A4SWIFT のクリーンアップ ツールでは、次の操作を実行します。  
  
-   実行**BM が展開解除**ForActivities.xml および MRSRBAM.xml に対する  
  
-   存在する場合、FrrActivities_ConnectionStrings.xml と MRSRActivities_ConnectionStrings.xml ファイルを削除します。  
  
-   存在する場合は、A4SWIFT 2.1 を削除 (にサーバーをアップグレードした場合[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]が、セットアップがインストールされている A4SWIFT 2.1 を左) および A4SWIFT 2.1 フォルダーを削除  
  
-   A4SWIFT のすべてのアセンブリを展開解除します。  
  
-   A4SWIFT の管理者グループと、A4SWIFT Users グループを削除します。  
  
-   A4SWIFT データベースを削除します  
  
-   A4SWIFT の仮想ディレクトリを削除します。  
  
-   完全なサイレント アンインストールを実行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]を削除し、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]フォルダー (選択した場合)  
  
 成果物を削除し、アセンブリを展開解除、クリーンアップ ツールもは次のとおり  
  
-   実行するためにインターネット インフォメーション サービス (IIS) 管理サービスを開始します  
  
-   停止し、MSSQLSERVER、SQLSERVERAGENT、BizTalk、およびエンタープライズ シングル サインオン サービスを再起動  
  
#### <a name="to-run-the-a4swift-cleanup-tool"></a>A4SWIFT のクリーンアップ ツールを実行するには  
  
1.  A4SWIFT のクリーンアップ ツールを実行する前に、A4SWIFT の既定のアセンブリのいずれかを参照する他のプロジェクトを展開解除します。  
  
2.  コマンド プロンプトを開きに移動\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for swift \sdk\tools です。  
  
3.  型**A4SWIFTCleanupTool.exe**キーを押します**ENTER**です。  
  
    > [!NOTE]
    >  A4SWIFTCleanupTool.exe を最初に実行すると、ヘルプ画面を表示され、パラメーターを入力するように求められます。 このツールは、パラメーターを入力するまでは実行されません。  
  
4.  ツールを実行するアクションに応じて、次のキーのいずれかを押すと**ENTER**:  
  
    -   **0**の (既定) が実行されるアクションがありません  
  
    -   **1**仮想ディレクトリとレジストリ設定を含め、コンピューター上のすべてのローカル A4SWIFT リソースを削除するには  
  
    -   **2**を Sharepoint Web フォルダー、FIN メッセージ テンプレート、BRE ポリシーとボキャブラリ、BizTalk アイテム、および A4SWIFT データベースを含む BizTalk Server グループ上のすべての共有 A4SWIFT リソースを削除するには  
  
    -   **3**すべてのローカルと共有リソースを削除するには  
  
    -   **4**すべてのローカルと共有リソースを削除すると、アンインストール、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]製品です。  
  
## <a name="see-also"></a>参照  
 [ツール](../../adapters-and-accelerators/accelerator-swift/tools.md)