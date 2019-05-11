---
title: BizTalk での mySAP アダプターでの EXECQUERY ステートメントの例 |Microsoft Docs
description: EXECQUERY の例と、mySAP アダプターを BizTalk アダプター パック (BAP) を使用したサンプル
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4139af16-7c38-4ea2-b3e5-5acf8fc1f3c4
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 631780b540d37e80c9218fc03f58b628e6d6e7d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373479"
---
# <a name="examples-for-execquery-statement"></a>EXECQUERY ステートメントの例
このトピックでは、EXECQUERY ステートメントの例を示します。  


## <a name="sample-statements"></a>サンプル ステートメント
-   P1 と P2 の 2 つのパラメーターを受け取るクエリを実行するコマンド。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262',@P2 = 'La Quinta Hotel & Towers'  
    ```  
  
-   P1 のパラメーターの値の範囲を受け取るクエリを実行するコマンドです。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   特定の範囲外パラメーター P1 の値を取得するクエリを実行するコマンド。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 BETWEEN '0000003262' AND '0000003265'  
    ```  
  
-   パラメーター P1 の 2 つの値のいずれかを実行するクエリを実行するコマンド。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '0000003262', @P1 = '0000003263'  
    ```  
  
-   特定のパラメーターの値をとることのできないクエリを実行するコマンド。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', NOT @P1 = '0000003262', NOT @P2 = '0000003263'  
    ```  
  
     この例では、P1 は '0000003262' 以外の値を持つことができます。 同様に、P2 では、'0000003263' 以外の値を持つことができます。  
  
-   SAP システムで定義されたバリアントを持つクエリを実行するコマンド。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant = ‘variant1’  
    ```  
  
     バリアントは、保存された一連の SAP クエリの実行中に指定できる選択条件を参照してください。 たとえば、バリアントを使用すると、クエリの既定値を指定します。 すべてのパラメーターに対して定義されているバリエーションがあるクエリでは、コマンド テキストでパラメーターを指定する必要はありません。  
  
-   パラメーターを必要としないクエリを実行するコマンド。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'some_dummy_value'  
    ```  
  
     パラメーターを受け取らないクエリでは、ダミーの値を持つパラメーターを指定する必要があります。  
  
-   日付の値を指定してください。 パラメーターを含むクエリを実行するコマンド。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = '20080606'  
    ```  
  
     日付の値を指定してください。 パラメーターを受け取るクエリでは、yyyymmdd 形式で指定として日付を指定する必要があります。  
  
-   パラメーターに null 値を指定することでクエリを実行するコマンド。  
  
     このようなクエリでは、としてクエリを指定することはできません。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 = 'null'  
    ```  
  
     代わりに、値を指定しない場合を指定しないでください P1 にします。  
  
-   特定の数よりも大きい値を指定してくださいパラメーターを含むクエリを実行するコマンド。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 > '0000003262'  
    ```  
  
-   値を指定してください。 パラメーターを含むクエリを実行するコマンドを特定の数よりも低い。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 < '0000003262'  
    ```  
  
-   特定の数以上の値を指定してくださいパラメーターを含むクエリを実行するコマンド。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 >= '0000003262'  
    ```  
  
-   小さいまたは特定の数と等しく、値を指定してくださいパラメーターを含むクエリを実行するコマンド。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 <= '0000003262'  
    ```  
  
-   値が特定の数と等しくありません必要パラメーターを含むクエリを実行するコマンド。  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1 != '0000003262'  
    ```  
  