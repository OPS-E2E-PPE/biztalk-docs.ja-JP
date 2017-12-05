---
title: "SchemaValidator |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, SchemaValidator utility
- validating, SchemaValidator utility
- SchemaValidator utility
- schemas, SchemaValidator utility
ms.assetid: 3bd61a03-d81e-4fd1-802c-f801000002d7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9e3921b8bf83e3e7e775efef77a029bfda2e7e9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="schemavalidator"></a>SchemaValidator
メッセージ インスタンスに関連した問題のトラブルシューティングを行うには、SchemaValidator ユーティリティを使用します。 検証に失敗したメッセージを受信した場合は、SchemaValidator ユーティリティを実行して、失敗の原因を特定できます。  
  
 このユーティリティは、使用中のアセンブリにスキーマの .dll ファイルが含まれているが、スキーマの .xsd ファイルを持っていない場合に使用します。 SchemaValidator ユーティリティでは、スキーマの .dll ファイルを使用して検証できます。  
  
## <a name="location-in-sdk"></a>SDK でのパス  
 \<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemavalidator  
  
## <a name="building-and-running-schemavalidator"></a>SchemaValidator のビルドと実行  
  
#### <a name="to-build-the-schemavalidator-utility"></a>SchemaValidator ユーティリティをビルドするには  
  
1.  コマンド プロンプトを開きます。  
  
2.  移動\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemavalidator です。  
  
3.  コマンド プロンプトで次のように入力します。 **sn-k SchemaValidator.snk**、ENTER キーを押します。  
  
4.  開始**Microsoft Visual Studio 2012**です。  
  
5.  **ファイル** メニューのをポイント**開く**、順にクリック**ソリューションを開く**です。  
  
6.  移動\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemavalidator、選択**SchemaValidator.sln**、クリックして**開く**です。  
  
7.  ソリューション エクスプ ローラーで右クリック**SchemaValidator**、クリックして**プロパティ**です。  
  
8.  **MessageInspector プロパティ** ページで **署名** タブをクリックして**アセンブリに署名**チェック ボックスをオンします。 選択**SchemaValidator.snk**で**厳密な名前キー ファイルを選択して**です。  
  
9. をクリックして**SchemaValidator.cs**です。  
  
10. `Main` の次の既存のコード行に適切なメッセージ インスタンス パスを入力します。  
  
    ```  
    const string xmlInstancePath = @"..\..\Sample3A4.xml";  
    ```  
  
11. `Main` の次の既存のコード行を RNPIP アセンブリへの参照に置き換えて、適切なスキーマを選択します。  
  
    ```  
    _3A4_MS_V02_02_PurchaseOrderRequest BTSSchema = new _3A4_MS_V02_02_PurchaseOrderRequest();  
    ```  
  
12. 右クリック**SchemaValidator**、クリックして**ビルド**です。  
  
13. メッセージ インスタンスを変更する削除して、テスト、 \< \!DOCTYPE しています.\>タグは、XML インスタンスのヘッダーから DTD ファイルを指定します。  
  
14. メッセージ インスタンスのルート ノードに、検証に使用するスキーマの XML 名前空間を追加します。  
  
    > [!NOTE]
    >  SchemaValidator ユーティリティによる検証する準備が整ったスキーマの例は、の Sample3A4.xml を参照してください\<*ドライブ*\>\Program Files\Microsoft BizTalk\<バージョン\>アクセラレータ。for rosettanet \sdk\schemavalidator です。  
  
15. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**SchemaValidator.cs**ユーティリティを実行するには、ctrl キーと F5 キーを押します。  
  
## <a name="remarks"></a>解説  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には SchemaValidator のコードが含まれているので、SchemaValidator にロジックを追加できます。 たとえば、SchemaValidator をコマンドライン ユーティリティにすることができます。  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)