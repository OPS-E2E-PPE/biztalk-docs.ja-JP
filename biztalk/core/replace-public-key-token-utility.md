---
title: パブリック キー トークンのユーティリティを置き換える |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Replace Public Key Token Utility
- utilities, Replace Public Key Token Utility
- public key token
ms.assetid: ed8673b9-af06-4bd7-b8b7-7371e4dd0fed
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d546a01d615dbd6dd8146d186e484addcef200b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996283"
---
# <a name="replace-public-key-token-utility"></a>公開キー トークンの置換ユーティリティ
このユーティリティを使用すると、ファイル内の公開キー トークンまたは変数のいずれかを、厳密な名前のアセンブリ キー (.snk) ファイルから抽出した公開キー トークンに置き換えることができます。  
  
 開発者が使用するスクリプトを記述する場合、このユーティリティが便利なあります、 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)アセンブリを展開します。 展開を成功させるには、アセンブリの完全修飾名を指定する必要があります。この完全修飾名には、アセンブリの公開キー トークンが含まれます。 アセンブリの公開キー トークンは、.snk ファイルから抽出され、アセンブリの構築時に割り当てられます。 ただし、アセンブリを新しい環境に展開する前に、別の公開キー トークンを使用してアセンブリを再構築することがしばしばあります。 その結果、展開スクリプトを実行する際に、アセンブリで使用される公開キー トークンを開発者が知らないという状況が生じます。  
  
 公開キー トークンの置換ユーティリティを使用してこの状況に対処するには、次の 2 つの方法があります。  
  
-   **シナリオ 1。** 開発者は、公開キー トークンまたはそれを表すプレースホルダーのいずれかを展開スクリプト内で使用できます。 ユーザーは、スクリプトを実行する前に、公開キー トークンの置換ユーティリティを使用して、スクリプト ファイル内の公開キー トークンまたはプレースホルダーを、.snk ファイル (展開先の環境に合わせてアセンブリを構築する際に使用されたもの) から抽出した公開キー トークンに置き換えることができます。  
  
-   **シナリオ 2。** 開発者が自動的に次のように新しい公開キー トークンを置換するスクリプトを構成できます。 スクリプトの先頭には、公開キー トークンの置換ユーティリティを呼び出すと、公開キー トークンを含む .snk ファイルをポイントします。 公開キー トークンを表す環境変数 %NEWTOKEN% をスクリプト内で使用します。 スクリプトの実行時に、ユーティリティは、.snk ファイルから公開キー トークンの値を抽出し、その値を環境変数 %NEWTOKEN% に設定します。 スクリプトの実行時に、%NEWTOKEN% の各インスタンスが、指定された .snk ファイルの公開キー トークンに置き換えられます。 以下に例を示します。  
  
    ```  
    ReplacePKT.bat key.snk  
    ...  
    ...  
    gacutil /u Assembly, ... PublicKey=%NEWTOKEN% ...  
    ```  
  
## <a name="location-in-sdk"></a>SDK でのパス  
 公開キー トークンの置換ユーティリティは次の場所にあります。  
  
 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\ReplacePublicKeyToken\\します。  
  
 公開キー トークンの置換ユーティリティは次の 3 つのファイルから構成されます。  
  
-   ReplacePKT.bat  
  
-   ReplacePKT.vbs  
  
-   ReplacePKT.wsf  
  
## <a name="procedures"></a>手順  
 シナリオ 1 の説明に従って、ファイル内の公開キー トークンまたはプレースホルダーのインスタンスを、.snk ファイルから抽出した公開キー トークンに置き換えるには、次の手順を使用します。  
  
#### <a name="to-replace-instances-of-a-public-key-token-or-a-placeholder-in-a-file"></a>ファイル内の公開キー トークンまたはプレースホルダーのインスタンスを置き換えるには  
  
1. 公開キー トークンの置換ユーティリティの 3 つのファイル (ReplacePKT.bat、ReplacePKT.vbs、および ReplacePKT.wsf)、スクリプト ファイル、および .snk ファイルがローカル コンピューターに存在していることを確認します。  
  
2. コマンド ウィンドウで、公開キーの置換ユーティリティのファイルを含むフォルダーにディレクトリを変更します。  
  
3. コマンド プロンプトから次のコマンドを実行します。  
  
4. **ReplacePKT \<**  *.snk ファイル* **\> \<** *古い公開キー トークン* **\>\<** *ファイルを置き換える* **\>**  
  
   |オプション|説明|  
   |------------|-----------------|  
   |**\<** *.snk ファイル* **\>**|既存の公開キー トークンまたはプレースホルダーと置き換える公開キー トークンが含まれている .snk ファイルの完全パス。|  
   |**\<** *古い公開キー トークン* **\>**|置換対象の公開キー トークンまたはプレースホルダー。|  
   |**\<** *ファイルを置き換える* **\>**|置換対象の公開キー トークンまたはプレースホルダーが含まれているファイルの完全パス。|  
  
    例:  
  
    **ReplacePKT.bat C:\Tokens\MyToken.snk 12ab3456cd789e12 C:\Scripts\MyScript.vbs**  
  
   シナリオ 2 の説明に従って、.snk ファイルから抽出した公開キー トークンを使用するスクリプト内の環境変数を自動的に設定するには、次の手順を使用します。  
  
#### <a name="to-set-an-environment-variable-that-uses-a-public-key-token"></a>公開キー トークンを使用する環境変数を設定するには  
  
1.  スクリプト ファイルの先頭に次のコード行を追加します。  
  
    ```  
    ReplacePKT <filename>.snk  
    ```  
  
     場所\< *filename* \>公開キー トークンを取得する .snk ファイルの名前を指定します。  
  
    ```  
    Example: ReplacePKT.bat MyToken.snk  
    ```  
  
2.  公開キー トークンを表す `%NEWTOKEN%` をスクリプト ファイル内で使用します。  
  
     例:  
  
    ```  
    PublicKey=%NEWTOKEN%  
    ```  
  
3.  スクリプト ファイルをユーザーに配布する場合は、公開キー トークンの置換ユーティリティを構成する 3 つのファイル (ReplacePKT.bat、ReplacePKT.vbs、および ReplacePKT.wsf) と共に配布します。 スクリプト コピーのユーザーが、スクリプトを実行する前に、これらのファイルをファイル システム上の同一のフォルダーにコピーしていることを確認します。  
  
## <a name="see-also"></a>参照  
 [SDK のユーティリティ](../core/utilities-in-the-sdk.md)