---
title: インストールに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 245379f2-4048-4803-83ea-38dc23eb1a81
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4bc572cc18ca7d9d5515fe9f189287df5d1440f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022952"
---
# <a name="read-the-installation-known-issues"></a>インストールをに関する既知の問題
[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] 既知の問題は、次のセクションに表示されます。  
  
## <a name="swift-does-not-support-stress-testing-on-integration-test-bed-itb-and-swiftnet-stub-environment"></a>SWIFT はストレス テスト ベッドの統合 (ITB) と SWIFTNet スタブ環境でテストをサポートしていません  
 ITB は、スループットの観点からサービス レベル アグリーメント (SLA) を指定しないと、データが完全に転送されるか、一貫性のあるであることを保証できません。 ストレスのテスト、パイロット環境でネットワークの運用環境に実装する必要があります。  
  
 さらに、すべてのノード (サーバー、線、および帯域幅) が、データの損失を回避するために正しく構成されていることを確認する必要があります。 スループットの一般的なサンプルを次に示します。  
  
- 高負荷のコンピューターに属する操作/Fileact の送信: 20 メッセージ/分  
  
- 高負荷のコンピューターに属する操作/Fileact の受信: 300 ~ 400 メッセージ/分  
  
  詳細については、SWIFT、マニュアルを参照してください。  
  
## <a name="messages-not-pushed-when-queue-is-open"></a>メッセージ キューが開いているときにプッシュされません。  
 キューとのセッションが開いており、メッセージがプッシュされていない場合は、対話または FileAct ストア アンド フォワード (SnF) モードを使用している、SNLreceiver.exe を再起動する必要があります。 SWIFT ときどき発生する問題を回避できます。  
  
## <a name="you-must-use-cdata-when-passing-characters-like--and--in-message"></a>などの文字を渡すときに使用して CDATA する必要があります"<"と"&"は、メッセージ  
 という用語は、CDATA のテキスト データ、XML パーサーで解析する必要があります。  文字"<"と"&"は XML 要素で無効です。 "<"、パーサーは、新しい要素の先頭として解釈されるので、エラーが生成されます。 "&"、パーサーは文字のエンティティの先頭として解釈されるので、エラーが生成されます。 CDATA セクション内のすべてのものは、パーサーによって無視されます。 CDATA セクションの開始"\<! [CDATA ["で終わる"]\>"  
  
## <a name="you-must-use-passthrough-pipelines-with-payload-only-mode"></a>ペイロードのみのモードでパススルー パイプラインを使用する必要があります。  
 InterAct アダプターのペイロードのみのモードを使用する場合は、パススルー パイプラインを使用して、両方の送信と受信ポートのカスタム パイプラインを使用していない場合する必要があります。  
  
## <a name="multiple-security-contexts-not-created-swiftnet-stub-computer"></a>複数のセキュリティ コンテキストを作成していない (SWIFTNet スタブ コンピューター)  
 SWIFTNet スタブ コンピューターで、複数のセキュリティ コンテキストは、別の送信ポートは作成されません。 ITB で複数のセキュリティ コンテキストが作成されます。