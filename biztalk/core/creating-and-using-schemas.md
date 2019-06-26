---
title: 作成し、TIBCO でスキーマの使用 |Microsoft Docs
description: BizTalk エディターを使用して、BizTalk adapter for TIBCO Enterprise Message Service、スキーマを作成して、スキーマの BizTalk Server のターゲットの名前空間を設定
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3927b0b3-db3b-4494-b003-d930af734e58
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 151ddefb45afd41c343b43de44786d7d99ff9b94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353671"
---
# <a name="create-and-use-tibco-schemas"></a>作成し、TIBCO スキーマを使用

## <a name="overview"></a>概要
Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) は、(オーケストレーションでは、アダプターを使用) 場合のみ、Visual Studio で、XML エディターまたは BizTalk Server のエディターを使って作成するスキーマを使用します。 スキーマと思われる情報の種類について説明します。 このトピックには、送信と受信ハンドラーの両方の情報が含まれています。  
  
スキーマを作成する使用の BizTalk adapter for TIBCO Enterprise Message Service には、ターゲットの名前空間が必要です。 BizTalk Server では、特定のメッセージ インスタンスを特定のオーケストレーションに関連付けられるキーのキーであるために、ターゲットの名前空間が必要です。 つまり、オーケストレーションを特定のターゲット名前空間を持つメッセージをサブスクライブしをそのターゲット名前空間を持つ受信 XML メッセージは、メッセージをサブスクライブしているすべてのオーケストレーションに与えられます。 XML ドキュメント スキーマがターゲットの名前空間を持たない場合、BizTalk Server は、キーとしてルート要素の名前を使用します。  

次の手順では、ターゲットの名前空間を設定する方法と、スキーマを生成する方法を示します。  
  
## <a name="generate-a-schema"></a>スキーマを生成します。    
 
1.  BizTalk エディターでは、プロジェクトを開きます。  
  
2.  右上でソリューション エクスプ ローラーの **追加**、し、**生成した項目の追加**します。  
  
3.  **テンプレート**ペインで、**スキーマの生成**、 をクリックし、**追加**します。  
  
4.  **スキーマの生成**] ダイアログ ボックスで、**ドキュメントの種類**一覧で、[**整形式 XML**します。  
  
5.  をクリックして**参照**をクリックして、スキーマを生成する入力ファイルを検索する**OK**。  
  
次に、ターゲットの名前空間を設定します。  
  
## <a name="set-the-target-namespace"></a>ターゲットの名前空間を設定します。  
  
1. BizTalk エディターで開き、スキーマ ファイルを右クリックして **\<スキーマ\>** 、し、**プロパティ**します。  
  
2. **プロパティ**ウィンドウで、検索、 **Namespace**フィールドし、たとえば、名前を入力`testNameSpace`します。  
  
   メッセージを使用してオーケストレーションを続行することができます。 メッセージが取得されて、BizTalk Server で、スキーマ セットのターゲットの名前空間を使用するオーケストレーションを検索し、オーケストレーション プロセスが実行します。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの開発](../core/developing-applications5.md)