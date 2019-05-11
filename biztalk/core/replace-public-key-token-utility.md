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
ms.openlocfilehash: 5754f9ee853f1501d247f1236ca89d158b3788c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397906"
---
# <a name="replace-public-key-token-utility"></a>パブリック キー トークンのユーティリティを置き換える
このユーティリティにいずれかの公開キー トークンまたは変数でファイルを厳密な名前のアセンブリ キー (.snk) ファイルから抽出した公開キー トークンに置き換えて使用できます。  
  
 開発者が使用するスクリプトを記述する場合、このユーティリティが便利なあります、 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)アセンブリを展開します。 展開を成功させるには、その公開キー トークンを含む、アセンブリの完全修飾名を指定する必要があります。 アセンブリの公開キー トークンは、.snk ファイルから抽出し、ビルド時に、アセンブリに割り当てられています。 アセンブリは、新しい環境に展開は、前にただし、多くの場合、再構築されます別の公開キー トークンを使用します。 結果として、開発者では、どのような公開キー トークンは、配置スクリプトの実行時にアセンブリに使用されますが知らないです。  
  
 このような状況に対処する公開キー トークンの置換ユーティリティを使用できる 2 つの方法はあります。  
  
-   **シナリオ 1。** 配置スクリプトでは、開発者は公開キー トークンまたは公開キー トークンを表すプレース ホルダーのいずれかを使用できます。 スクリプトを実行する前に、ユーザーは、公開キー トークンまたはスクリプト ファイル内のプレース ホルダーを送信先の環境のアセンブリを構築するために使用された .snk ファイルから抽出した公開キー トークンで代用する公開キー トークンの置換ユーティリティを実行できます。  
  
-   **シナリオ 2。** 開発者は、自動的に次のように新しい公開キー トークンを置換するスクリプトを構成できます。スクリプトの先頭には、公開キー トークンの置換ユーティリティを起動し、公開キー トークンを含む .snk ファイルをポイントします。 スクリプト内では、環境変数 %newtoken% を使用して、公開キー トークンを表します。 スクリプトを実行すると、このユーティリティは、.snk ファイルから公開キー トークンの値を抽出を環境変数 %newtoken% に設定。 スクリプトの実行時に %newtoken% の各インスタンスに置き換えられる、指定された .snk ファイルから公開キー トークン。 例 :  
  
    ```  
    ReplacePKT.bat key.snk  
    ...  
    ...  
    gacutil /u Assembly, ... PublicKey=%NEWTOKEN% ...  
    ```  
  
## <a name="location-in-sdk"></a>SDK でのパス  
 公開キー トークンの置換ユーティリティはあります。  
  
 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\ReplacePublicKeyToken\\します。  
  
 公開キー トークンの置換ユーティリティには、3 つのファイルが構成されています。  
  
-   ReplacePKT.bat  
  
-   ReplacePKT.vbs  
  
-   ReplacePKT.wsf  
  
## <a name="procedures"></a>手順  
 シナリオ 1」の説明に従って、.snk ファイルから抽出されたパブリック キー トークンを使用して公開キー トークンまたはプレース ホルダー ファイル内のすべてのインスタンスを置換するのにには、次の手順を使用します。  
  
#### <a name="to-replace-instances-of-a-public-key-token-or-a-placeholder-in-a-file"></a>公開キー トークンまたはファイル内のプレース ホルダーのインスタンスを置換するには  
  
1. 3 つのパブリック キー トークンの置換ユーティリティ ファイル (ReplacePKT.bat、ReplacePKT.vbs、および ReplacePKT.wsf)、スクリプト ファイル、および .snk ファイルがローカル コンピューターから使用可能なすべてを確認します。  
  
2. コマンド ウィンドウでは、公開キーの置換ユーティリティのファイルを含むフォルダーにディレクトリを変更します。  
  
3. コマンド プロンプトから次のコマンドを実行します。  
  
4. **ReplacePKT \<**  *.snk ファイル* **\> \<** *古い公開キー トークン* **\>\<** *ファイルを置き換える* **\>**  
  
   |オプション|説明|  
   |------------|-----------------|  
   |**\<** *.snk file* **\>**|既存の公開キー トークンまたはプレース ホルダーを使用する公開キー トークンを含む .snk ファイルの完全なパスに置き換えてください。|  
   |**\<** *古い公開キー トークン* **\>**|公開キー トークンまたはプレース ホルダーを置き換えます。|  
   |**\<** *ファイルを置き換える* **\>**|公開キー トークンまたはプレース ホルダーを置換するファイルの完全パス。|  
  
    例:  
  
    **ReplacePKT.bat C:\Tokens\MyToken.snk 12ab3456cd789e12 C:\Scripts\MyScript.vbs**  
  
   シナリオ 2」の説明に従って、.snk ファイルから抽出した公開キー トークンを使用するスクリプトで環境変数を自動的に設定するのにには、次の手順を使用します。  
  
#### <a name="to-set-an-environment-variable-that-uses-a-public-key-token"></a>公開キー トークンを使用する環境変数を設定するには  
  
1.  スクリプト ファイルの先頭には、次のコード行を追加します。  
  
    ```  
    ReplacePKT <filename>.snk  
    ```  
  
     場所\< *filename* \>公開キー トークンを取得する .snk ファイルの名前を指定します。  
  
    ```  
    Example: ReplacePKT.bat MyToken.snk  
    ```  
  
2.  スクリプト ファイルには、`%NEWTOKEN%`公開キー トークンを表すため。  
  
     例:  
  
    ```  
    PublicKey=%NEWTOKEN%  
    ```  
  
3.  スクリプト ファイルをユーザーに提供する場合に、(ReplacePKT.bat、ReplacePKT.vbs、および ReplacePKT.wsf)、公開キー トークンの置換ユーティリティを構成する 3 つのファイルが含まれます。 コピーしてください、スクリプトのユーザーのすべてのファイル、ファイル システム上の同じフォルダーにスクリプトを実行する前にします。  
  
## <a name="see-also"></a>参照  
 [SDK のユーティリティ](../core/utilities-in-the-sdk.md)