---
title: BRE 配置ユーティリティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BRE Deployment utility
- deploying, BRE Deployment utility
ms.assetid: 5b04592c-ea1e-4ded-8ca4-dcd051d6375e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5868172b566a12ab6299e0eaabe12fa2153bfb97
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966816"
---
# <a name="bre-deployment-utility"></a>BRE 配置ユーティリティ
BRE 配置ユーティリティを使用を発行し、ビジネス ルール エンジン (BRE) ボキャブラリと SWIFT スキーマに必要なポリシーを展開することができます。 メッセージの種類の BRE 検証を有効にするには、公開およびこれらのボキャブラリおよびポリシーの展開が必要です。  
  
 SWIFT 標準リリース ガイド (SRGs) を使用して、必要な規則を識別するしを使用して、ビジネス ルールを展開することも、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ボキャブラリとポリシーを展開するビジネス ルール作成ツールです。 ただし、BRE 配置ユーティリティを使用することははるかに簡単です。  
  
 BRE 配置ユーティリティの実行、次の場合。  
  
-   指定した展開済みのアセンブリを調査し、アセンブリの展開されているメッセージ スキーマを決定します。  
  
-   発行、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_CodeLists.xml と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]に必要な _Functions.xml ボキャブラリ[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]ビジネス ルールの処理です。  
  
-   ポリシーを展開、SWIFT 基本 (参照ポリシー、パーティの識別子のポリシー、およびネットワーク ルール ポリシー) メッセージ スキーマに関連付けられているし、発行します。  
  
-   公開し、マスター ポリシーと各メッセージ スキーマに関連付けられている検証ポリシーを展開します。  
  
-   これは、すべての手順を示すログ ファイルを生成します。 このファイルで BREDeploymentLog.txt、 \<*ドライブ*\>: \Documents and settings \all \all Data フォルダーです。  
  
    > [!NOTE]
    >  BRE 配置ユーティリティ配置しません BIC マスター ポリシーおよび BIC 検証ポリシー。 ルール エンジン展開ウィザードを使用して、これらを展開する必要があります。  
  
    > [!NOTE]
    >  インストールした場合[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]で既定以外のディレクトリ (C:\Program files \microsoft 以外[!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)])、または 64 ビット コンピューターで作業している、BRE 配置ユーティリティは正しく動きません内のパスを変更するまで、BREDeployment.exe.config ファイルです。 この構成ファイルにある、 \<*ドライブ*\>: \Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\SDK\Tools フォルダーです。 ユーティリティの構成を更新するには、メモ帳で、BREDeployment.exe.config を開き、基本ポリシー、スキーマ、およびボキャブラリのディレクトリのフォルダーを変更します。  
  
 配置ユーティリティを使用して、展開解除と、ポリシーとボキャブラリを非公開にこのプロセスを反転させることができますも。 このユーティリティが両方の展開を機能の展開を解除します。  
  
### <a name="to-use-the-bre-deployment-utility"></a>BRE 配置ユーティリティを使用するには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk Accelerator 用 SWIFT**、順にクリック**BRE 配置ユーティリティ**です。  
  
2.  BRE 配置ユーティリティでクリックして**参照**です。  
  
3.  展開済みのアセンブリまたはアセンブリの公開、ボキャブラリとポリシーを展開し、をクリックしたい選択**OK**です。  
  
4.  をクリックして**展開**です。  
  
    > [!NOTE]
    >  そのアセンブリを展開するスキーマに基づいて、BRE 配置ユーティリティは、プロセス実行を関連するルールを特定し、BRE を使用するために発行することです。 完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ:**配置が完了したら**です。 ビジネス ルール作成ツールを使用すると、展開の成功を確認します。  
  
    > [!NOTE]
    >  ポリシーとボキャブラリを展開解除する をクリックして**Undeploy**です。 展開解除プロセスは、他の展開済みのポリシーによって使用される可能性があります A4SWIFT_CodeLists.xml と A4SWIFT_Functions.xml ボキャブラリを展開解除されません。  
  
5.  検索\<*ドライブ*\>: ファイル BREDeploymentLog.txt の \Documents and settings \all \all データをユーティリティには、ログが作成されたことを確認します。  
  
    > [!NOTE]
    >  各配置手順を確認するテキスト エディターを使用して、ログ ファイルを開くことができます。  
  
## <a name="see-also"></a>参照  
 [ツール](../../adapters-and-accelerators/accelerator-swift/tools.md)