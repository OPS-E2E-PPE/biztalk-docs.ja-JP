---
title: BAM 定義を展開する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, definitions [BAM]
- managing [BAM definitions], deploying definitions
- definitions [BAM], deploying
- Deploy-All command [BAM]
ms.assetid: 02b8888c-6f6c-45dd-8445-6e507a02f5f0
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58d2711ee5bdf9e280ad32610031d5720d8d2c36
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385277"
---
# <a name="how-to-deploy-bam-definitions"></a>BAM 定義を展開する方法
管理者を使用して、**展開すべて**Excel ブックまたは XML 定義ファイルから BAM 定義を展開する BAM 管理ユーティリティのコマンドは、ブックからエクスポートします。 完全なインストールを実行するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、構成ウィザードでは、BAM 構成 XML は、自動的に構成されます。  
  
> [!NOTE]
>  複数のユーザーは、Excel 用 BAM アドインで作業は場合、は、同じバージョンの Microsoft Data Access Components (MDAC) があることをお勧めします。 それ以外の場合、互換性の問題が発生する可能性があります。 具体的には、新しいバージョンの MDAC を使用しているコンピューターで、テンプレートを作成し、古いバージョンの MDAC を使用しているコンピューターでそれを開こうとする場合、コンパイラ エラーが発生します。  
  
> [!NOTE]
>  データ ディメンション (場所など) ごとの 1 つだけのデータ項目 (たとえば、City) を使用することができます。 リージョンなどの別のデータ ディメンションでは、市区町村をもう一度使用できません。  
  
> [!IMPORTANT]
>  これらを展開する前に、BAM Excel ブック (.xls) のセキュリティを確認することをお勧めします。 管理コンピューターに Excel を使用すると、BAM Excel ブックのセキュリティを確認できます。 ブックを展開する前に開くし、マクロのセキュリティは、高に設定され、警告がないことを確認します。  
  
> [!IMPORTANT]
>  BAM データベースで、"bam _\<.\>"すべての SQL エンティティの名前付け規則は予約されています (テーブル、インデックス、ストアド プロシージャ、ロールなど.)。*しない*この名前付け規則を使用して、SQL エンティティを作成する。 このような使用状況は、未定義の動作を、可能性があります。  
  
 BAM 定義 XML ファイルを展開する前に、このファイルを作成するために使用するロケールをデプロイしているコンピューターのロケールと一致していることを確認する必要があります。 たとえば、日本語版の Microsoft Windows を実行しているコンピューター上のファイルを作成する場合でファイルを展開するコンピューターは日本語のロケールを設定する必要があります。 ファイルとコンピューターの設定が一致しない場合は、使用して適切なロケールに、BAM 管理ユーティリティを実行するコンピューターを切り替える必要があり、ユーティリティを実行する前に再起動する必要があります。  
  
> [!NOTE]
>  すべての言語を使用して、同じコード ページ、または 2 つだけの言語が含まれます、1 つは英語でない限り、BAM 定義 XML ファイルは複数の言語でテキストを含めることはできません。  
  
 コンピューターのロケール設定を変更する方法の詳細については、オペレーティング システムのヘルプを参照してください。  
  
### <a name="to-deploy-a-bam-definition"></a>BAM 定義を展開するには  
  
1.  次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2.  入力して、追跡フォルダーに移動します**C:\Program files \microsoft BizTalk Server\<バージョン\>\Tracking**コマンド プロンプトでします。 **Enter**キーを押します。  
  
3.  型**bm 展開すべて-definitionfile:\<BAM 定義ファイル\>** します。  
  
4.  **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)