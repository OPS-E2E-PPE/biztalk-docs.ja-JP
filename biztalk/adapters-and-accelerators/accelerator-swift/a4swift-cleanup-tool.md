---
title: A4SWIFT クリーンアップ ツール |Microsoft Docs
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
ms.openlocfilehash: 494225194e3b302acb868277696054260b7c1a07
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65527552"
---
# <a name="a4swift-cleanup-tool"></a>A4SWIFT クリーンアップ ツール
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]クリーンアップ ツールでは、Microsoft のあるサーバーを準備できます。[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]の新規インストール用にインストールされている[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]します。 このツールは、A4SWIFT の成果物など、契約、部門、およびビジネス ルール エンジン (BRE) ポリシーを削除し、アセンブリが展開解除されます。 ツールを実行して、多くの A4SWIFT アイテムを手動で削除しないようにすることができ、他のアセンブリから参照する場合があるアセンブリを展開解除の問題が解決します。  
  
 クリーンアップ ツールを実行すると、アイテムを削除した後、コンピューター (既定)、またはアンインストール A4SWIFT にインストールされている A4SWIFT 保持するための選択肢があります。 A4SWIFT をアンインストールする前に、ツールを実行する必要があります。  
  
> [!CAUTION]
>  運用環境で、A4SWIFT クリーンアップ ツールを使わないでください。 ツールの目的は、マルチ サーバー展開ではなく、1 台のサーバーの開発環境で使用します。  
  
> [!NOTE]
>  既定では、クリーンアップ ツールはその他の言語が英語以外は機能しません。 ただし、クリーンアップ ツールは、ローカライズされたコンピューターで動作するよう環境を変更することができます。 FormPublish ツール、t パラメーターとテンプレート ドキュメント ライブラリのローカライズされた文字列を使用して実行**t:VorLagen**ドイツ語の環境にします。 ローカライズされた環境のクリーンアップ ツールを実行できます。  
  
 次がありますクリーンアップ ツールを実行する場合は true。  
  
- メンバーがあります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
- [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] ツールを実行するサーバーにインストールする必要があります。  
  
- MrsrConfiguration.dll、Shared.dll、および RuleEngineExtension.dll は、ツールを実行するサーバーに配置する必要があります。  
  
## <a name="what-the-cleanup-tool-does"></a>クリーンアップ ツールでは、  
 A4SWIFT クリーンアップ ツールは、次の操作を実行します。  
  
- 実行**BM が展開解除**ForActivities.xml と MRSRBAM.xml に対して  
  
- 存在する場合に、FrrActivities_ConnectionStrings.xml と MRSRActivities_ConnectionStrings.xml ファイルを削除します  
  
- 存在する場合は、A4SWIFT 2.1 を削除します (サーバーをアップグレードした場合[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]セットアップがインストールされている A4SWIFT 2.1 を左が) と A4SWIFT 2.1 フォルダーを削除します  
  
- A4SWIFT のすべてのアセンブリを展開解除します。  
  
- A4SWIFT の管理者グループと A4SWIFT ユーザー グループを削除します。  
  
- A4SWIFT データベースを削除します。  
  
- A4SWIFT の仮想ディレクトリを削除します  
  
- 完全なサイレント アンインストールを実行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]し、削除、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]フォルダー (選択) 場合  
  
  成果物を削除し、アセンブリを展開解除、クリーンアップ ツールは次の処理。  
  
- 実行するためにインターネット インフォメーション サービス (IIS) 管理サービスを開始します。  
  
- 停止し、MSSQLSERVER、SQLSERVERAGENT、BizTalk、およびエンタープライズ シングル サインオン サービスを再起動し、  
  
#### <a name="to-run-the-a4swift-cleanup-tool"></a>A4SWIFT クリーンアップ ツールを実行するには  
  
1. A4SWIFT クリーンアップ ツールを実行する前に、A4SWIFT の既定のアセンブリのいずれかを参照する任意のプロジェクトを展開解除します。  
  
2. コマンド プロンプトを開きに移動\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for swift \sdk\tools します。  
  
3. 型**A4SWIFTCleanupTool.exe**しキーを押します**ENTER**します。  
  
   > [!NOTE]
   >  最初に A4SWIFTCleanupTool.exe を実行して、ツール、ヘルプ画面を表示します。 パラメーターを入力するように求められます。 このツールは、パラメーターを入力するまでは実行されません。  
  
4. ツールを実行するアクションに応じて、次のキーを押してし、キーを押します**ENTER**:  
  
   - **0**の (既定値) の取得操作はありません  
  
   - **1** 、仮想ディレクトリとレジストリ設定を含め、コンピューター上のすべてのローカル A4SWIFT リソースを削除するには  
  
   - **2** Sharepoint Web フォルダー、FIN メッセージ テンプレート、BRE ポリシーとボキャブラリ、BizTalk アイテム、および A4SWIFT データベースなど、BizTalk Server グループ上のすべての共有 A4SWIFT リソースを削除するには  
  
   - **3**ローカルと共有リソースを削除するには  
  
   - **4**をローカルと共有リソースを削除し、アンインストール、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]製品です。  
  
## <a name="see-also"></a>参照  
 [ツール](../../adapters-and-accelerators/accelerator-swift/tools.md)