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
ms.openlocfilehash: c2a9bac75fd3cb71210fdfff99978d973f28c142
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284072"
---
# <a name="customizing-a-private-process-to-work-with-a-specific-pip"></a>特定の PIP に使用するプライベート プロセスのカスタマイズ
処理するプライベート プロセス オーケストレーションまたはプロセスのインスタンスの特定のプロセス PIP (Partner Interface) いない応答側が発生するフィルター式を作成することができます。 これは、受信および特定の PIP インスタンスを処理するカスタム プライベート プロセスを作成して、プロセスを使用して既定のプライベート プロセスにその他のすべての PIP インスタンスの柔軟性をによりします。  
  
 PIP または複数の特定の Pip の特定の作業のカスタム プライベート プロセスを作成するには、プライベート プロセス オーケストレーションの受信図形のフィルター式を作成します。 例としては、Microsoft® で PIP3A4PrivateResponder.odx オーケストレーション[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SDK。 場所は\<*ドライブ*\>: \Program Files\BizTalk\<バージョン\>Accelerator for rosettanet \sdk\pip3a4process を使用して Business rules \pip3a4privateresponder にあります。  
  
 だけでなく、特定の PIP のインスタンスのみを処理するプライベート プロセスを作成するには、その PIP のインスタンスを処理しないように、既定の BTARN プライベート プロセスをカスタマイズする必要があります。  
  
### <a name="to-customize-a-responder-private-process-to-work-with-a-specific-pip"></a>特定の PIP を使用する応答側プライベート プロセスをカスタマイズするには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、特定の PIP を操作するためのカスタム応答側プライベート プロセス オーケストレーションを作成します。 既定の BTARN 応答側プライベート プロセス オーケストレーションのオーケストレーションを基にすることができます。  
  
   > [!NOTE]
   >  既定値を検索する応答側プライベート プロセス オーケストレーション、BTARN SDK PrivateResponder.odx という名前です。 場所は*\<ドライブ\>*: \Program Files\BizTalk\<バージョン\>Accelerator for rosettanet \sdk\privateresponder です。  
  
2. カスタム オーケストレーションを BizTalk プロジェクトに追加します。 プロジェクトに Microsoft.Solutions.BTARN.GlobalSchemas.dll ファイルへの参照があることを確認してください。  
  
3. オーケストレーション デザイナーでカスタム オーケストレーションを開きます。  
  
4. 1 つ目を右クリックして**受信**図形をオーケストレーションをアクティブ化し、をクリックし、**フィルター式の編集**します。  
  
   > [!NOTE]
   >  既定の BTARN 応答側プライベート プロセス オーケストレーションの受信図形には、2 つのフィルター条件があります。Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory = ="AsyncAction"または Microsoft.Solutions.BTARN.GlobalSchemas.SCCategory ="SyncAction"です。 この式は、オーケストレーションが RosettaNet メッセージを処理することを確認します。 カスタム オーケストレーションには、このフィルター式を保持します。  
  
5. **フィルター式**ダイアログ ボックスで、最初の開いている行のプロパティの列で選択**microsoft.solutions.btarn.globalschemas.scpipcode** 演算子 列で、ドロップダウン リストから選択**==** 値 列に入力 3 桁の PIP コードの例では、型のボックスの一覧から**3A4**します。  
  
6. **[OK]** をクリックします。  
  
7. オーケストレーション デザイナーでは、既定の応答側プライベート プロセス オーケストレーション プロジェクト (PrivateResponder.btproj) を開きます。 プロジェクトに Microsoft.Solutions.BTARN.GlobalSchemas.dll ファイルへの参照が含まれることを確認します。  
  
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