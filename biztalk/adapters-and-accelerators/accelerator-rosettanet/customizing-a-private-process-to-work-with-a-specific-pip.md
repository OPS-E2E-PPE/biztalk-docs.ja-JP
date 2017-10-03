---
title: "特定の PIP に使用するプライベート プロセスをカスタマイズする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private processes, PIPs
- private processes, customizing
- developing, private processes
- PIPs, private processes
- customizing private processes
ms.assetid: 88494e87-25a0-4c94-9396-61a0e07964aa
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec579716f9ab02389ce9f2d5ae5ec02ef0b30730
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="customizing-a-private-process-to-work-with-a-specific-pip"></a>特定の PIP で使用するプライベート プロセスのカスタマイズ
応答側のプライベートプロセス オーケストレーションが特定の Partner Interface Process (PIP) のインスタンスを処理するかどうかを指定するフィルター式を作成できます。 これにより、特定の PIP インスタンスを受信して処理するためのカスタム プライベート プロセスを作成し、その他の PIP インスタンスには既定のプライベート プロセスを使用する柔軟性が備わります。  
  
 特定の PIP で使用するカスタム プライベート プロセスを作成するには、プライベートプロセス オーケストレーションの受信図形のフィルタ式を作成します。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK の PIP3A4PrivateResponder.odx オーケストレーションがその一例です。 これは、 \<*ドライブ*>: \Program Files\BizTalk\<バージョン > Accelerator for rosettanet \sdk\pip3a4process を使用してビジネス \pip3a4privateresponder です。  
  
 特定の PIP のインスタンスのみを処理するプライベート プロセスを作成するだけでなく、既定の BTARN プライベート プロセスをカスタマイズして、その PIP のインスタンスを処理しないように設定する必要があります。  
  
### <a name="to-customize-a-responder-private-process-to-work-with-a-specific-pip"></a>特定の PIP で使用する応答側プライベート プロセスをカスタマイズするには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] で、特定の PIP で使用する応答側プライベートプロセス オーケストレーションを作成します。 既定の BTARN 応答側プライベートプロセスのオーケストレーションを基盤にできます。  
  
    > [!NOTE]
    >  PrivateResponder.odx という名前の既定の応答側プライベートプロセス オーケストレーションは BTARN SDK にあります。 これは、 *\<ドライブ >*: \Program Files\BizTalk\<バージョン > Accelerator for rosettanet \sdk\privateresponder です。  
  
2.  カスタム オーケストレーションを BizTalk プロジェクトに追加します。 プロジェクトに Microsoft.Solutions.BTARN.GlobalSchemas.dll ファイルへの参照があることを確認してください。  
  
3.  オーケストレーション デザイナでカスタム オーケストレーションを開きます。  
  
4.  1 つを右クリックして**受信**図形をクリックして、オーケストレーションをアクティブに**フィルタ式の編集**です。  
  
    > [!NOTE]
    >  既定の BTARN 応答側プライベートプロセス オーケストレーションの受信図形には、Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "AsyncAction" または Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "SyncAction" という 2 つのフィルター条件があります。 この式は、オーケストレーションが RosettaNet メッセージを処理することを確認します。 カスタム オーケストレーションにこのフィルター式を維持してください。  
  
5.  **フィルター式**ダイアログ ボックスで、最初の空白行の プロパティ 列で選択**Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**ドロップダウン リストから、演算子 列選択 **==** ドロップダウン リストから値 列に 3 桁の PIP コードの例については、型と入力します。 **3A4**です。  
  
6.  **[OK]**をクリックします。  
  
7.  オーケストレーション デザイナーで既定の応答側プライベートプロセス オーケストレーション プロジェクト (PrivateResponder.btproj) を開きます。 プロジェクトに Microsoft.Solutions.BTARN.GlobalSchemas.dll ファイルへの実際の参照があることを確認してください。  
  
8.  ダブルクリックして**PrivateResponder.odx**です。  
  
9. 右クリックし、 **[receivefrompublicprocessresponder]**受信図形をクリックして**フィルタ式の編集**です。  
  
10. **フィルター式**ダイアログ ボックスで、最初の空白行の [プロパティ] 列で選択**Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode**ドロップダウン リストからです。 [演算子] 列で選択**! =**ドロップダウン リストからです。 [値] 列で、3 桁の PIP コードの例については、型を入力"**3A4"**です。  
  
11. **[OK]**をクリックします。  
  
12. ソリューション エクスプ ローラーでオーケストレーションを含むプロジェクトを右クリックし、をクリックして**ビルド**です。  
  
13. プロジェクトが正常にビルドされたら、プロジェクトを右クリックし、をクリックして**展開**です。  
  
14. **ファイル** メニューのをポイント**開く**、順にクリック**プロジェクト**です。  
  
15. 移動\<*ドライブ*>: \Program Files\BizTalk\<バージョン > Accelerator for rosettanet \sdk\privateresponder、選択**PrivateResponder.odx**をクリックして**[Ok]**です。  
  
16. ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[ビルド]**をクリックします。  
  
17. プロジェクトが正常にビルドされたら、プロジェクトを右クリックし、をクリックして**展開**です。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)