---
title: 関連付けセット |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- correlation sets, inspecting
- correlation sets, about correlation sets
- correlation sets, passing as parameters
- messages, correlation sets
- correlation sets
- correlation sets, following correlation sets
- correlation sets, initializing
ms.assetid: 528dcd6c-d364-4bb8-8deb-cd4a0791867f
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1767755e240171431b01d5997691b800fdbdaa3b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354387"
---
# <a name="correlation-sets"></a>関連付けセット
この種のオーケストレーション インスタンスとメッセージの関連付けは、関連付けセットを定義することで実現できます。 関連付けセットは、プロパティのセットを*値を指定して*します。 これは、プロパティの一覧だけである関連付けの種類によって異なります。 受信メッセージがこれらすべてのプロパティにもない場合は、ごとに一致するには、値とは、相関関係の失敗し、オーケストレーション インスタンスによって、メッセージを受信できませんが。  
  
 関連付けの種類は、一連のメッセージに関連付けするプロパティを定義します。 BizTalk の基本インストールの一部としてインストールされる GlobalPropertySchemas と共に展開「システム」プロパティを含む一部の BizTalk プロジェクトで以前プロパティ スキーマで定義され、展開のプロパティを指定できます。 関連付けセットは、特定のオーケストレーションによって処理されるメッセージを含める必要があるこれらのプロパティのプロパティと値のセットを定義します。  
  
 たとえば、関連付けの種類が、次のプロパティで構成できます。  
  
|関連付けの種類のプロパティ|使用可能な XML 表現|  
|-------------------------------|---------------------------------|  
|社会保障番号|\<SSN\>\</SSN\>|  
|生年月日|\<DOB\>\</DOB\>|  
|Gender|\<性別\>\<性別/\>|  
  
 この関連付けの種類から派生した関連付けセットは、次のプロパティの値で構成できます: 中  
  
|相関関係プロパティと値の設定|可能な XML 表現|  
|-------------------------------------|---------------------------------|  
|社会保障番号 = 222112222|\<SSN\>222112222\</SSN\>|  
|誕生日 =「1/1/1995」|\<DOB\>「1/1/1995」\</DOB\>|  
|Gender = Male|\<性別\>M\<性別/\>|  
  
> [!NOTE]
>  各関連付けセットには、最大 3 つのパラメーターがサポートしています。  
  
## <a name="initializing-correlation-sets"></a>イニシャライズ関連付けセット  
  
-   **受信アクションで初期化される関連付けセット**  
  
     アクションでは、存在する必要があるプロパティの正確なセットを定義、対応するで処理するために、公開されたメッセージの受信時に初期化される関連付けセットでは、オーケストレーションのアクションが表示されます。 イニシャライズ関連付けセットは、ドキュメント内の対応する値に基づいて関連付けの種類から関連付けセットを作成します。  
  
-   **送信アクションで初期化される関連付けセット**  
  
     送信アクションで初期化される関連付けセットは、ドキュメント内の対応する値に基づいて関連付けの種類から作成し、送信ドキュメントに関連付けのプロパティを昇格させます。  
  
## <a name="following-correlation-sets"></a>フォロー関連付けセット  
 フォロー関連付けセットは、非アクティブにのみバインドできます受信アクションまたは送信アクションにします。 フォロー関連付けセットは、以前に初期化された関連付けセットと連携して指定されます。  
  
-   **受信アクションにバインドされたフォロー関連付けセット**  
  
     フォロー関連付けセットの受信アクションにバインドされたプロパティと、ドキュメントが受信するために含める必要がある値のセットを定義します。  受信アクション フォロー関連付けセット、以前に初期化された関連付けセットからのプロパティを含むドキュメントを許可します。  
  
-   **送信アクションにバインドされたフォロー関連付けセット**  
  
     フォロー関連付けセットの送信アクションにバインドされている関連付けセット内のプロパティのセットが送信ドキュメントに昇格させることに影響します。  
  
## <a name="inspecting-correlation-sets"></a>関連付けセットの調査  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 関連付けセットを調査できるようにをします。 関連付けセットには、次のようなコードを使用して、式図形を検査できます。  
  
```  
MsgLen = Correlation_1(BTS.MessageLength);  
```  
  
 上記の例は、という名前の変数を作成したことが前提としています**MsgLen**型の**System.Int16**オーケストレーションに相関関係が含まれているとは、名前付きセット**Correlation_1**. 関連付けセットを調査する機能は、別のオーケストレーションによってオーケストレーションに渡された関連付けの値を検査する必要がある場合に役立ちます。 可能性があります。  
  
## <a name="passing-correlation-sets-as-parameters-to-orchestrations"></a>関連付けセットを渡すパラメーターとしてオーケストレーションへ  
 としての相関関係を渡すことができます*で*他のオーケストレーションにパラメーター。