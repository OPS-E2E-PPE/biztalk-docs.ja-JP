---
title: 特定の PIP に使用するプライベート プロセスのカスタマイズ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, PIPs
- private processes, customizing
- developing, private processes
- PIPs, private processes
- customizing private processes
ms.assetid: 88494e87-25a0-4c94-9396-61a0e07964aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77abdf870f0813bb5b9e1dd7a039b99ef0726c15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001507"
---
# <a name="customizing-a-private-process-to-work-with-a-specific-pip"></a>特定の PIP に使用するプライベート プロセスのカスタマイズ
応答側のプライベートプロセス オーケストレーションが特定の Partner Interface Process (PIP) のインスタンスを処理するかどうかを指定するフィルター式を作成できます。 これにより、特定の PIP インスタンスを受信して処理するためのカスタム プライベート プロセスを作成し、その他の PIP インスタンスには既定のプライベート プロセスを使用する柔軟性が備わります。  
  
 特定の PIP で使用するカスタム プライベート プロセスを作成するには、プライベートプロセス オーケストレーションの受信図形のフィルタ式を作成します。 例としては、Microsoft® で PIP3A4PrivateResponder.odx オーケストレーション[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SDK。 場所は\<*ドライブ*\>: \Program Files\BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pip3a4process を使用して Business rules \pip3a4privateresponder にあります。  
  
 特定の PIP のインスタンスのみを処理するプライベート プロセスを作成するだけでなく、既定の BTARN プライベート プロセスをカスタマイズして、その PIP のインスタンスを処理しないように設定する必要があります。  
  
### <a name="to-customize-a-responder-private-process-to-work-with-a-specific-pip"></a>特定の PIP で使用する応答側プライベート プロセスをカスタマイズするには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] で、特定の PIP で使用する応答側プライベートプロセス オーケストレーションを作成します。 既定の BTARN 応答側プライベートプロセスのオーケストレーションを基盤にできます。  
  
   > [!NOTE]
   >  PrivateResponder.odx という名前の既定の応答側プライベートプロセス オーケストレーションは BTARN SDK にあります。 場所は*\<ドライブ\>*: \Program Files\BizTalk\<バージョン\>Accelerator for rosettanet \sdk\privateresponder です。  
  
2. カスタム オーケストレーションを BizTalk プロジェクトに追加します。 プロジェクトに Microsoft.Solutions.BTARN.GlobalSchemas.dll ファイルへの参照があることを確認してください。  
  
3. オーケストレーション デザイナでカスタム オーケストレーションを開きます。  
  
4. 1 つ目を右クリックして**受信**図形をオーケストレーションをアクティブ化し、をクリックし、**フィルター式の編集**します。  
  
   > [!NOTE]
   >  既定の BTARN 応答側プライベートプロセス オーケストレーションの受信図形には、Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "AsyncAction" または Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory == "SyncAction" という 2 つのフィルター条件があります。 この式は、オーケストレーションが RosettaNet メッセージを処理することを確認します。 カスタム オーケストレーションにこのフィルター式を維持してください。  
  
5. **フィルター式**ダイアログ ボックスで、最初の開いている行のプロパティの列で選択**microsoft.solutions.btarn.globalschemas.scpipcode** 演算子 列で、ドロップダウン リストから選択**==** 値 列に入力 3 桁の PIP コードの例では、型のボックスの一覧から**3A4**します。  
  
6. **[OK]** をクリックします。  
  
7. オーケストレーション デザイナーで既定の応答側プライベートプロセス オーケストレーション プロジェクト (PrivateResponder.btproj) を開きます。 プロジェクトに Microsoft.Solutions.BTARN.GlobalSchemas.dll ファイルへの実際の参照があることを確認してください。  
  
8. ダブルクリック**PrivateResponder.odx**します。  
  
9. 右クリックし、 **[receivefrompublicprocessresponder]** 受信図形をクリックして**フィルター式の編集**します。  
  
10. **フィルター式**ダイアログ ボックスで、最初の開いている行のプロパティの列で選択 **[microsoft.solutions.btarn.globalschemas.scpipcode]** ドロップダウン リストから。 [演算子] 列で選択 **! =** ドロップダウン リストから。 [値] 列で、入力 3 桁の PIP コードの例では、型の"**3A4"** します。  
  
11. **[OK]** をクリックします。  
  
12. ソリューション エクスプ ローラーでオーケストレーションを含むプロジェクトを右クリックし、クリックして**ビルド**します。  
  
13. プロジェクトがビルドされたら、プロジェクトを右クリックし、**デプロイ**します。  
  
14. **ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト**。  
  
15. 移動\<*ドライブ*\>: \Program Files\BizTalk\<バージョン\>Accelerator for rosettanet \sdk\privateresponder には、選択**PrivateResponder.odx**、 をクリックし、 **OK**します。  
  
16. ソリューション エクスプローラーで、プロジェクトを右クリックし、 **[ビルド]** をクリックします。  
  
17. プロジェクトがビルドされたら、プロジェクトを右クリックし、**デプロイ**します。  
  
## <a name="see-also"></a>参照  
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)