---
title: 手順 3:アセンブリに厳密な名前を割り当てる |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies
- message enrichment tutorial, strong name assemblies
- strong name assemblies
ms.assetid: 8709e4e1-b428-42af-ba3c-08225c17a9eb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01e98a471e2c91c463b7ead725cef61be1a52d92
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288919"
---
# <a name="step-3-assign-a-strong-name-to-the-assembly"></a>手順 3:アセンブリに厳密な名前を割り当てます
この手順で作成して割り当てるの厳密な名前、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アセンブリ。 厳密な名前のアセンブリは、いくつかのセキュリティの利点しがグローバル アセンブリ キャッシュ (GAC) にプロジェクトを配置するために必要です。 厳密な名前では、デジタル署名と一意キーのペアを割り当てることで、アセンブリの一意性を保証します。 これもだれ以降のバージョンのアセンブリを生成できることを確認して、アセンブリの系統を保護します。 最後に、厳密な名前は、アセンブリの内容がのビルド以降に変更していないことを保証するために厳密な整合性チェックを提供します。  
  
### <a name="to-assign-a-strong-name-to-the-assembly"></a>アセンブリに厳密な名前を割り当てる  
  
1. 開始**Visual Studio コマンド プロンプト**します。  
  
   > [!NOTE]
   >  厳密な名前キーを既に作成している場合は、再利用することができます。  
  
2. コマンド プロンプトに移動します<strong>\<*ドライブ*\>: \Tutorial\BTAHL7V22Common</strong> (場所\<*ドライブ*\>は。インストール ドライブ文字) とキーを押します**Enter**します。  
  
3. コマンド プロンプトで「 **sn – k key.snk**、押します **」と入力**します。 あることを示すメッセージが表示されます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]キー ファイルの key.snk にキーのペアを作成します。  
  
4. ソリューション エクスプ ローラーで右クリックし、 **BTAHL7V22Common**プロジェクトをクリックして**プロパティ**します。  
  
5. BTAHL7V22Common プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**します。  
  
6. 右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンを順にクリックします。  
  
7. アセンブリ キー ファイル ダイアログ ボックスを参照 **\<*ドライブ*\>: \Tutorial\BTAHL7V22Common\key.snk**、 をクリックして**オープン**、順にクリックします**OK**します。  
  
8. ソリューション エクスプ ローラーで右クリックして**BTAHL7V22Common**、 をクリックし、**デプロイ**します。 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 次のプロジェクトから参照できるアセンブリを作成します。  
  
9. BTAHL7V2XCommon プロジェクトに対して手順 4 ~ 8 を繰り返します。  
  
   続行する[手順 4。スキーマの作成](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)