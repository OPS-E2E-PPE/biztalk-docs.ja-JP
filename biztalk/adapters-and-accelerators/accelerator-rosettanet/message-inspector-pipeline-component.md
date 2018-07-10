---
title: Inspector パイプライン コンポーネントのメッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipelines, custom pipelines
- pipelines, Message Inspector Pipeline Component
- Message Inspector Pipeline Component
- pipelines, creating
ms.assetid: d9c00718-c8cd-4289-8f58-e4edc61b9a05
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b7b0a20e584771a41c6732bccbdf017efe29517
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966867"
---
# <a name="message-inspector-pipeline-component"></a>Message Inspector パイプライン コンポーネント
このパイプライン コンポーネントにより、マルチパート メッセージのすべての部分、およびメッセージ コンテキストを確認し、メッセージに問題があるかどうかを判断できます。 このコンポーネントはトラブルシューティングの目的で使用します。  
  
 このパイプライン コンポーネントにより、XML ファイルは指定されたディレクトリにドロップされます。 これらの各ファイルは、RNIFv2.0 メッセージの 4 つの部分 (Preamble Header、Delivery Header、Service Header、Service Content) のいずれか、または RNIFv1.1 メッセージの 3 つの部分 (Preamble Header、Service Header、Service Content) のいずれかを含んでいます。 もう 1 つの XML ファイルは、メッセージ コンテキストを含んでいます。  
  
 このコンポーネントは、カスタム パイプラインに構築し、送信ポートに接続します。 送信ポートにフィルタを作成し、監視するメッセージをサブスクライブします。 このトラブルシューティングは、その Microsoft® を処理する標準だけでなく[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]既にを実行します。  
  
## <a name="building-a-custom-pipeline-using-the-message-inspector-pipeline-component"></a>Message Inspector パイプライン コンポーネントを使用したカスタム パイプラインの構築  
 Message Inspector パイプライン コンポーネントを使用するには、このコンポーネントを含むカスタム パイプラインを構築し、展開する必要があります。 詳細については、」を作成するパイプライン「パイプライン デザイナーで BizTalk Server のヘルプを参照してください。  
  
#### <a name="to-deploy-the-message-inspector-pipeline-component"></a>Message Inspector パイプライン コンポーネントを展開するには  
  
1. Visual Studio を起動します。  
  
2. **ファイル**メニューで、**オープン**、 をクリックし、**プロジェクト**。  
  
3. C:\Program Files (x86) \microsoft BizTalk 移動\<バージョン\>Accelerator for rosettanet \sdk\message Inspector Pipeline Component 選択 **[messageinspector.csproj]**、順にクリックします**開いている**します。  
  
4. Visual Studio コマンド プロンプトを開きます。  
  
5. コマンド プロンプトで C:\Program Files (x86) \microsoft BizTalk 移動\<バージョン\>Accelerator for rosettanet \sdk\message Inspector Pipeline component \obj\debug します。  
  
6. コマンド プロンプトで「 **"sn-k MessageInspector.snk"** キーを作成し、ENTER キーを押します。  
  
7. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリック**MessageInspector**、] をクリックし、**プロパティ**します。  
  
8. **MessageInspector プロパティ**] ページで [**署名**タブをクリックし、をクリックし、**アセンブリに署名**チェック ボックスをオンします。  
  
9. **厳密な名前キー ファイルを選択して**ドロップダウンで、C:\Program Files (x86) \microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\message Inspector Pipeline component \obj\debug と選択**MessageInspector.snk**し**オープン**します。  
  
10. ソリューション エクスプ ローラーで右クリック**MessageInspector**、 をクリックし、**ビルド**します。 出力ペインで、ビルドが成功したことを確認します。  
  
11. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリックします**Windows エクスプ ローラー**します。  
  
12. [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、C:\Program Files (x86) \Microsoft BizTalk への移行\<バージョン\>Accelerator for rosettanet \sdk\message Inspector Pipeline component \obj\debug を右クリックして **[Microsoft.solutions.btarn.sdk.messageinspector.dll]**、] をクリックし、**コピー**します。  
  
13. C:\Program Files (x86) \microsoft BizTalk 移動\<バージョン\>Accelerator for rosettanet \pipeline Components を右クリックして**パイプライン コンポーネント**、順にクリックします**貼り付け**.  
  
14. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  
  
15. **新しいプロジェクト** ダイアログ ボックスで、テンプレート ペインで**空の BizTalk Server プロジェクト**の**名前**ボックスに、プロジェクトの名前を入力します。 **場所**ボックスに、プロジェクトを保存するフォルダーに移動してクリックして**OK**します。  
  
16. ソリューション エクスプ ローラーでプロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の追加**します。  
  
17. **新しい項目の追加**ダイアログ ボックスで、**送信パイプライン**の**名前**ボックスで、カスタム パイプライン ファイルの名前を入力し、クリックして**を開く**.  
  
    > [!NOTE]
    >  Message Inspector パイプライン コンポーネントは、受信ポートではなく、送信ポートのみに追加します。  
  
18. [ツールボックス] ウィンドウの BizTalk パイプライン コンポーネント ペイン内を右クリックし、**アイテムの追加/削除**します。  
  
19. **ツールボックスのカスタマイズ** ダイアログ ボックスで、 **BizTalk パイプライン コンポーネント** タブで  **BTARN Message Inspector Component**、順にクリックします**ok**.  
  
20. [ツールボックス] ウィンドウの [BizTalk パイプライン コンポーネント] ウィンドウで、クリックして押したまま**BTARN Message Inspector Component**のコンポーネントをドラッグし、**ここにドロップ!** ◆セグ ： 前の TU に含まれる◇  
  
21. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで、パイプライン プロジェクトの名前を右クリックし、順にクリックします**プロパティ**します。  
  
22. **プロパティ ページ**ダイアログ ボックスで、をクリックして**共通プロパティ**、順にクリックします**アセンブリ**します。  
  
23. 関連付けられているテキスト ボックスに、右側のウィンドウで**アセンブリ キー ファイル**、省略記号をクリックしますは、C:\Program Files (x86) \Microsoft BizTalk に進みます。\<バージョン\>Accelerator for rosettanet \sdk\message Inspector。Pipeline component \obj\debug を選択します**MessageInspector.snk**、 をクリックし、 **OK**します。  
  
24. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]パイプライン デザイナーでは、選択、 **BTARN Message Inspector Component**図形。  
  
25. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、**ディレクトリ**ボックスに、XML ファイルをドロップするディレクトリの名前を入力します。  
  
26. ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**ビルド**します。 ビルドが成功することを確認します。  
  
27. ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**デプロイ**します。 展開が成功することを確認します。  
  
28. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ビュー** メニューのをクリックして**BizTalk エクスプ ローラー**です。  
  
29. 右クリックして**送信ポート**、 をクリックし、**送信ポートの追加**します。  
  
30. **新しい送信ポートを作成**ダイアログ ボックスで、をクリックして**OK**します。  
  
31. **送信ポートのプロパティ** ダイアログ ボックスで、**名前**で、送信ポートの名前を入力ボックスに、**プライマリ**左側のウィンドウで選択されていること、**トランスポートの種類**クリックし、右側のウィンドウで**ファイル**します。  
  
32. **送信ポートのプロパティ** ダイアログ ボックスで、**アドレス (URI)** ボックスで、省略記号ボタンをクリックします (**.**).  
  
33. **FILE トランスポートのプロパティ**ダイアログ ボックスで、型、**先**、フォルダー名 をクリックして**送信**左側のウィンドウ、次の**送信パイプライン**右側のウィンドウで、先ほど作成したカスタム パイプラインを選択します。  
  
34. をクリックして**フィルターし、マップ**左側のウィンドウでクリック**フィルター**します。  
  
35. 右側のペインにフィルター式を入力し、パイプラインで XML ファイルをドロップするファイルの種類を指定します。 すべての RNIF v1.1 メッセージ ファイルを削除する場合など**プロパティ**Microsoft.Solutions.BTARN.Schemas.RNIFv11.GlobalBusinessAction を選択および**演算子**場合"Exists"を選択し、クリックして**OK**します。  
  
36. BizTalk エクスプローラで、先ほど作成した送信ポートを右クリックして**参加**送信ポートを再度右クリックし、クリックして**開始**します。  
  
## <a name="remarks"></a>コメント  
 通常の処理では、一度に確認できるのはメッセージの一部分 (オーケストレーションでメッセージの本文として指定した部分) のみです。 したがって、BizTalk 管理コンソールではメッセージの一部分しか確認できないため、トラブルシューティングの能力も限定されます。 Message Inspector パイプライン コンポーネントを使用して、この制限を克服するのに役立ちます。  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
