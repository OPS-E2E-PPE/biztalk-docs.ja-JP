---
title: BRE 配置ユーティリティ |Microsoft Docs
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
ms.openlocfilehash: d59a06b55e4d30e9e87a68adbf830dad38578f3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378973"
---
# <a name="bre-deployment-utility"></a>BRE 配置ユーティリティ
BRE 配置ユーティリティを発行して、ビジネス ルール エンジン (BRE) のボキャブラリと SWIFT スキーマに必要なポリシーの展開に使用することができます。 メッセージの種類の BRE 検証を有効にするには、公開およびこれらのボキャブラリおよびポリシーの展開が必要です。  
  
 SWIFT 標準リリース ガイド (SRGs) を使用して、必要なルールを識別する、Microsoft を使用して、ビジネス ルールをデプロイすることもできます。[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ボキャブラリおよびポリシーを展開するビジネス ルール作成ツールです。 ただし、BRE 配置ユーティリティを使用して、はるかに簡単です。  
  
 BRE 配置ユーティリティの実行、次の場合。  
  
- 指定した展開済みのアセンブリを調べ、アセンブリの展開されたメッセージのスキーマを決定します。  
  
- 発行、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_CodeLists.xml と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Functions.xml ボキャブラリが必要な Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]ビジネス ルールを処理します。  
  
- 発行し、SWIFT 基本ポリシー (ポリシーの参照、パーティの識別子のポリシーおよびネットワーク ルールのポリシー メッセージ スキーマに関連付けられている) を展開します。  
  
- 発行し、マスター ポリシーと各メッセージ スキーマに関連付けられている検証ポリシーを展開します。  
  
- 必要なすべての手順を示すログ ファイルを生成します。 このファイルで BREDeploymentLog.txt、 \<*ドライブ*\>: \Documents and バックアップ データを別のフォルダー。  
  
  > [!NOTE]
  >  BRE 配置ユーティリティをデプロイしません BIC マスター ポリシーおよび BIC 検証ポリシー。 ルール エンジン展開ウィザードを使用してこれらを展開する必要があります。  
  > 
  > [!NOTE]
  >  インストールした場合[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]で既定以外のディレクトリ (C:\Program files \microsoft 以外[!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)])、または 64 ビット コンピューターで作業して、BRE 配置ユーティリティは正しく動作しません内のパスを変更するまで、BREDeployment.exe.config ファイルです。 この構成ファイルにある、 \<*ドライブ*\>: \Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\SDK\Tools フォルダー。 ユーティリティの構成を更新するには、メモ帳で BREDeployment.exe.config を開き、基本ポリシー、スキーマ、およびボキャブラリのディレクトリのフォルダーを変更します。  
  
  展開解除ポリシーとボキャブラリの発行を取り消すと、このプロセスを反転させる配置ユーティリティを使用することもできます。 ユーティリティは、デプロイ両方がし、機能の展開を解除します。  
  
### <a name="to-use-the-bre-deployment-utility"></a>BRE 配置ユーティリティを使用するには  
  
1.  クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk Accelerator for SWIFT**、順にクリックします**BRE 配置ユーティリティ**します。  
  
2.  BRE 配置ユーティリティでクリックして**参照**します。  
  
3.  展開済みのアセンブリまたはアセンブリの発行、ボキャブラリとポリシーを展開し、クリックする選択**OK**します。  
  
4.  クリックして**デプロイ**します。  
  
    > [!NOTE]
    >  そのアセンブリを展開するスキーマに基づき、BRE 配置ユーティリティは、関連するルールを識別して、BRE を使用するための発行のプロセス。 完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ。**配置が完了したら**します。 ビジネス ルール作成ツールを使用すると、展開の成功を確認します。  
  
    > [!NOTE]
    >  ポリシーとボキャブラリを展開解除する をクリックして**Undeploy**します。 展開解除プロセスは、展開されているその他のポリシーで使用することが A4SWIFT_CodeLists.xml と A4SWIFT_Functions.xml ボキャブラリを展開解除されません。  
  
5.  検索\<*ドライブ*\>: \Documents and ユーティリティには、ログが作成されたことを確認する場合のバックアップ データ ファイルの BREDeploymentLog.txt します。  
  
    > [!NOTE]
    >  ログ ファイルを開くには、テキスト エディターを使用して、各デプロイの手順を確認します。  
  
## <a name="see-also"></a>参照  
 [ツール](../../adapters-and-accelerators/accelerator-swift/tools.md)