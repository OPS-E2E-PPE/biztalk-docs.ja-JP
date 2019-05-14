---
title: SchemaValidator |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, SchemaValidator utility
- validating, SchemaValidator utility
- SchemaValidator utility
- schemas, SchemaValidator utility
ms.assetid: 3bd61a03-d81e-4fd1-802c-f801000002d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2be96f3d87cb0744ca4e823942f7265bf6b3fa3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281976"
---
# <a name="schemavalidator"></a>SchemaValidator
メッセージ インスタンスに関する問題のトラブルシューティングを行うには、SchemaValidator ユーティリティを使用します。 検証に失敗したメッセージを受信する場合は、エラーの原因を特定、SchemaValidator ユーティリティを実行できます。  
  
 スキーマの .dll ファイルを含むアセンブリを使用している場合、このユーティリティを使用して、スキーマの .xsd ファイルがありません。 SchemaValidator ユーティリティを使用して、スキーマの .dll ファイルを使用して検証できます。  
  
## <a name="location-in-sdk"></a>SDK でのパス  
 \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\SchemaValidator  
  
## <a name="building-and-running-schemavalidator"></a>SchemaValidator のビルドと  
  
#### <a name="to-build-the-schemavalidator-utility"></a>SchemaValidator ユーティリティを構築するには  
  
1. コマンド プロンプトを開きます。  
  
2. 移動\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemavalidator します。  
  
3. コマンド プロンプトで「 **sn-k SchemaValidator.snk**、し、ENTER キーを押します。  
  
4. 開始**Microsoft Visual Studio 2012**します。  
  
5. **ファイル**メニューで、**オープン**、 をクリックし、**ソリューションを開く**。  
  
6. 移動\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemavalidator、選択**SchemaValidator.sln**、 をクリックし、**オープン**します。  
  
7. ソリューション エクスプ ローラーで右クリックして**SchemaValidator**、 をクリックし、**プロパティ**します。  
  
8. **MessageInspector プロパティ**] ページで [**署名**タブをクリックし、をクリックし、**アセンブリに署名**チェック ボックスをオンします。 選択**SchemaValidator.snk**で**厳密な名前キー ファイルを選択して**します。  
  
9. クリックして**SchemaValidator.cs**します。  
  
10. 次の既存のコードの行に適切なメッセージ インスタンス パスを入力`Main`:  
  
    ```  
    const string xmlInstancePath = @"..\..\Sample3A4.xml";  
    ```  
  
11. 次の既存のコードの行を置き換えます`Main`Rnpip アセンブリ、および選択し、適切なスキーマへの参照。  
  
    ```  
    _3A4_MS_V02_02_PurchaseOrderRequest BTSSchema = new _3A4_MS_V02_02_PurchaseOrderRequest();  
    ```  
  
12. 右クリック**SchemaValidator**、 をクリックし、**ビルド**します。  
  
13. メッセージ インスタンスを変更するのには削除して、テストする、 \< \!DOCTYPE.\>タグは、XML インスタンスのヘッダーから DTD ファイルを指定します。  
  
14. メッセージ インスタンスのルート ノードに対して検証するスキーマの XML 名前空間を追加します。  
  
    > [!NOTE]
    >  SchemaValidator ユーティリティによる検証準備が整ったスキーマの例は、Sample3A4.xml を参照してください\<*ドライブ*\>\Program Files (x86) \Microsoft BizTalk\<バージョン\>。Accelerator for rosettanet \sdk\schemavalidator します。  
  
15. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、 をクリックして**SchemaValidator.cs**とユーティリティを実行するには、ctrl キーと f5 キーを押します。  
  
## <a name="remarks"></a>コメント  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には SchemaValidator のコードが含まれています、ロジックは、ユーティリティを追加することができます。 たとえば、行うことができますが、コマンド ライン ユーティリティ。  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
