---
title: "インストールの既知の問題を読み取る |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 245379f2-4048-4803-83ea-38dc23eb1a81
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6641e7974a0e1872b71794af6553d708e9619dd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="read-the-installation-known-issues"></a>既知の問題のインストールします。
[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]既知の問題は、次のセクションに表示されます。  
  
## <a name="swift-does-not-support-stress-testing-on-integration-test-bed-itb-and-swiftnet-stub-environment"></a>SWIFT は統合テスト ベッド (ITB) および SWIFTNet スタブ環境でのテストのストレスをサポートしていません  
 ITB は、スループットの観点からサービス レベル アグリーメント (SLA) を提供せず、データが完全に転送されるか、一貫性のあることを保証できません。 ストレス テスト、パイロット運用環境でネットワークの運用環境に実装する必要があります。  
  
 さらに、すべてのノード (サーバー、線、および帯域幅) は、データの損失を避けるために正しく構成されていることを確認する必要があります。 スループットの典型的な例を次に示します。  
  
-   操作/Fileact のストレスがコンピューターに属する送信: 20 メッセージ/分  
  
-   操作/Fileact が高負荷のコンピューターに属する受信: 300 ~ 400 メッセージ/分  
  
 詳細については、迅速な対応は、マニュアルを参照してください。  
  
## <a name="messages-not-pushed-when-queue-is-open"></a>メッセージ キューを開いている場合にプッシュされません。  
 キューとのセッションが開いていて、メッセージがプッシュされるされなかった場合は、対話または FileAct ストア アンド フォワード (SnF) モードを使用している、SNLreceiver.exe を再起動する必要があります。 これは、ときどき発生する可能性が SWIFT の問題を回避できます。  
  
## <a name="you-must-use-cdata-when-passing-characters-like--and--in-message"></a>などの文字を渡すときに使用する CDATA 必要があります"<"と"&"は、メッセージに  
 という用語は、CDATA、XML パーサーで解析してはなりませんテキスト データに関するします。  などの文字"<"と"&"の XML 要素では無効です。 "<"、パーサーは、新しい要素の開始として解釈するために、エラーが発生します。 "&"、パーサーは文字エンティティの開始として解釈するために、エラーが発生します。 CDATA セクション内のすべてのものは、パーサーによって無視されます。 CDATA セクションの開始"\<! [CDATA ["で終わると"]\>"  
  
## <a name="you-must-use-passthrough-pipelines-with-payload-only-mode"></a>ペイロードのみのモードでパススルー パイプラインを使用する必要があります。  
 InterAct アダプターのペイロードのみのモードを使用している場合、両方の送信パススルー パイプラインを使用して、カスタム パイプラインを使用していない場合、受信ポートください。  
  
## <a name="multiple-security-contexts-not-created-swiftnet-stub-computer"></a>複数のセキュリティ コンテキスト (SWIFTNet スタブ コンピューター) は作成されません。  
 SWIFTNet スタブ コンピューター上の異なる送信ポートの複数のセキュリティ コンテキストは作成されません。 複数のセキュリティ コンテキストは、ITB に作成されます。